---
title: กฎและสูตร (Rules & Formula)
---

## 1. กฎ

> **ทุกตัวเลขในกาชาคือ BASE ที่เขียนด้วยมือครั้งเดียวต่อ banner type และ SCALE ที่เป็นเลขคณิตล้วน
> บนสมาชิกของ pool ระหว่างสองอย่างนี้ไม่มีอะไรถูกพิมพ์ด้วยมือ**

**BASE** (เขียนครั้งเดียว): ลำดับความหายาก `ord[r]` · ตาราง band rate `B[r]` ที่รวมได้ 1 พอดี ·
featured share `u` · weight ต่อ entry `w[i]` · ขนาด multi `K` · discount `d` · ราคา `c` ·
pity threshold `P[r]` · ช่วง reach ที่ยอมรับได้ `tau` · shard ต่อ duplicate `S[r]` · ladder `L[r][k]` ·
`rho` = ทศนิยมของ column ที่เก็บ rate

**ที่เหลือ DERIVE ทั้งหมด**: เรตของตัวละครหนึ่งตัว = band rate × within-band share

หัวใจอยู่ 4 บรรทัดนี้:

1. **`B` เป็นฟังก์ชันของ banner TYPE เท่านั้น** — ไม่อ่าน pool size ไม่อ่านจำนวนตัวละคร
   ไม่อ่านความคืบหน้าของ asset ⇒ **โรสเตอร์โตเปลี่ยนได้แค่ว่าใครอยู่ใน pool ไม่เคยเปลี่ยนเรต**
2. **ผลรวมเท่ากับ 1 พอดี ไม่ใช่ "ภายใน tolerance"** — สมาชิกตัวสุดท้ายของแต่ละแบนด์ดูดเศษปัดเข้าตัวเอง
3. **ตัวเลขที่ผู้เล่นเห็น = แถวเดียวกับที่ server สุ่ม** ทุกตัว ไม่มีเลขไหนถูกพิมพ์ซ้ำใน UI / docs /
   test / client config
4. **invariant ทุกข้อคือ assertion ที่ทำให้ build พัง** ไม่ใช่ให้ผู้เล่นเป็นคนเจอ

---

## 2. สูตร

```
-- ============ BASE (เขียนครั้งเดียว ไม่เคยต่อตัวละคร ไม่เคยต่อเคส) ============
ord[r]        rarity ordinal, หนึ่งชุดต่อเกม  (common < rare < epic < legendary)
B[type][r]    band rate ต่อ banner TYPE
u             featured share ของแบนด์ตัวเอง, 0 <= u < 1
w[i]          weight ต่อ entry, integer >= 1, default 1
K, d, c       multi size, discount, ราคาต่อครั้ง
P[r]          pity threshold (นับเป็น pull เต็มจำนวน); infinity = แบนด์นั้นไม่มี pity
tau_min, tau_max   ช่วง reach fraction ที่ยอมรับได้
S[r]          shard ต่อ duplicate ของ rarity r
L[r][k]       shard ที่ต้องใช้ถึงดาว k
rho           ทศนิยมของ rate column  (numeric(8,7) => rho = 7)

-- ============ SCALE (derive ทั้งหมด ไม่เคยพิมพ์) ============
pool_r  = { i : rarity(i) = r }              N_r = |pool_r|
feat_r  = { i in pool_r : featured(i) }      F_r = |feat_r|
W_r     = SUM(w[i] for i in pool_r)

share(i) = u * (featured(i) ? 1/F_r : 0) + (1 - u) * w[i] / W_r
           -- featured อยู่ในเศษที่เหลือด้วย ไม่ได้ถูกกันออก
           -- นิยามถูกต้องที่ N = 1, 2, 7, 50 โดยไม่มี special case

ideal(i) = B[rarity(i)] * share(i)

-- residual absorption: absorber = สมาชิกที่ id มากสุดในแบนด์ (deterministic)
rate(i)        = round(ideal(i), rho)                        ถ้า i ไม่ใช่ absorber
rate(absorber) = B[r] - SUM(rate(j) for j != absorber)
=> SUM(rate(i) ในแบนด์) = B[r] พอดี ทุก N_r >= 1
=> SUM(rate(i) ทั้ง pool) = SUM(B[r]) = 1 พอดี

cost(n) = c                        ถ้า n == 1
        = ceil(K * c * (1 - d))    ถ้า n == K

-- ============ PITY (derive) ============
pity_rarity = r ที่ ord[r] สูงสุด ในบรรดา r ที่ B[r] > 0 และ N_r >= 1
q           = B[pity_rarity]
pity ยิงเมื่อ counter + 1 >= P          -- ต้องพลาดติดกัน P-1 ครั้ง
forced draw = สุ่ม share(i) ภายในแบนด์นั้น    -- ไม่ใช่ order-by-id-limit-1
counter reset = 0 เมื่อได้ rarity ที่ ord >= ord[pity_rarity], ไม่งั้น +1

reach    = (1 - q)^(P - 1)              -- สัดส่วน cycle ที่ไปถึงเพดาน pity จริง
E[cycle] = (1 - (1 - q)^P) / q          -- pull เฉลี่ยต่อการได้ 1 ครั้ง

-- ============ DELIVERED RATE (สิ่งที่ผู้เล่นได้จริง ไม่ใช่ base) ============
D[pity_rarity] = 1 / E[cycle]
D[r]           = B[r] * (1 - D[pity_rarity]) / (1 - q)     สำหรับ r != pity_rarity
D_char(i)      = D[rarity(i)] * share(i)
=> SUM(D[r]) = 1

-- ============ SHARD / LADDER (derive) ============
shards_granted(i)    = is_new(i) ? 0 : S[rarity(i)]
pulls_to_terminal(i) = SUM(L[rarity(i)][k]) / (S[rarity(i)] * D_char(i))
```

**จุดที่คนพลาดบ่อยสุดคือ `D` กับ `B`** — `B` คือเรต base ที่ประกาศ แต่ผู้เล่นได้ `D` ซึ่งรวมผลของ pity
แล้ว ถ้าประกาศแค่ `B` โดยไม่พูดถึง `D` เลย ตัวเลขที่ประกาศจะต่ำกว่าความจริงเสมอ — และถ้า `P` เล็กมาก
มันจะต่ำกว่าแบบตลก ๆ (`P=1` ส่งของแบนด์บน 100% ขณะที่ประกาศ 5%)

---

## 3. INVARIANT — สิ่งที่ทำให้กฎนี้เป็นกฎ ไม่ใช่คำแนะนำ

แต่ละข้อคือ assertion ที่ทำให้ build พัง แต่ละข้อฆ่าบั๊กที่ระบุชื่อได้ ไม่ใช่บั๊กสมมติ
**ทุกข้อต้องรันเป็น automated test ใน CI ทุก commit ที่แตะ BASE value — checklist มือเป็นแค่ fallback ตอน CI ยังไม่ครอบคลุม**

| # | invariant | ถ้าไม่มี จะพังยังไง |
| --- | --- | --- |
| **I1** | `SUM(B[r]) == 1` พอดีที่ rho และ `0 < B[top] < 1` | — |
| **I2** | `SUM(rate(i)) == 1` **พอดี** ด้วย residual absorption ไม่ใช่ tolerance | tolerance ไม่ scale ตาม N — pool 20 ตัวพัง 74.3% ของเคส, pool 50 ตัวพัง 89.4% |
| **I3** | `B[r] > 0 => N_r >= 1` | pity ถูกบังคับให้เลือกจากแบนด์ที่ไม่มีสมาชิก แล้ว hard-error ถาวร |
| **I3b** | `B[r] = 0 => N_r = 0` | ตัวละครที่เรต 0% โผล่ใน list แต่สุ่มไม่ได้ |
| **I4** | `0 < B[pity_rarity] < 1` | pool ที่ทุกตัวเป็น pity rarity → counter ค้างที่ 0 ตลอดกาล |
| **I5b** | `SUM(D[r]) == 1` และหน้าจอต้องแสดง delivered ไม่ใช่แค่ base | `P=1` ส่งแบนด์บน 100% ขณะประกาศ 5% |
| **I5c** | % ต่อตัวที่แสดง == `round(100*rate(i), rho)` ทุกตัว | เรต featured ไม่มี assertion → pool โต 20 เท่าโดยเงียบสนิท |
| **I6** | `publishable(banner) <=> invariant ทุกข้อผ่าน AND ทุกตัวผ่าน asset gate` | banner ที่ disclosure ผิดยัง publish ได้ |
| **I7** | `w[i] >= 1` (integer) | `w = 0` → division by zero ทุก pull ทุกผู้เล่น; `w < 0` → เรตติดลบ |
| **I8** | แถวที่ผู้เล่น (role `anon`) เห็น == แถวที่ sampler อ่าน | test รันเป็น superuser → พิสูจน์ odds ของ row set ที่ผู้เล่นอ่านไม่ได้ |
| **I9** | `tau_min <= (1-q)^(P-1) <= tau_max` | `B[top]=0.30` → pity ยิงทุก 103,520 pull โดย invariant อื่นเขียวหมด |
| **I10** | `u > 0 => F_r >= 1` (ไม่มี fallback `u = 0`) | ถอด featured ออกเพราะ asset ไม่พร้อม → เรตตัวที่เหลือกระโดด 8 เท่า และยัง publish |
| **I11** | `rate(i) >= 10^-rho` ทุกตัว | แถวเรต 0 ผูก cumulative กับตัวก่อนหน้า → เกิด tie ใน `limit 1` |
| **I12** | monotone rarity: เรตสูงสุดในแบนด์ที่หายากกว่า < เรตต่ำสุดในแบนด์ที่พบง่ายกว่า | legendary กลายเป็นตัวที่พบบ่อยที่สุดใน pool |
| **I13** | monotone grind: `pulls_to_terminal(หายากกว่า) >= pulls_to_terminal(พบง่ายกว่า)` | `S` แยกตาม rarity แต่ `L` ไม่แยก → ตัวหายากที่สุดจบก่อน เกมสั้นลง 5.4 เท่า |
| **I14** | ค่าคงที่ที่กระจายอยู่หลายที่ (`K`, `L`, `ord`, `rho`) ต้องตรงกับ base | Postgres CHECK ใช้ subquery ไม่ได้ → literal ของ `K` 3 ชุดและ `L` 2 ชุดรอดกฎ |
| **I15** | ไม่มีแถว pity ของ (banner, rarity) ที่ไม่ใช่ pity_rarity ปัจจุบัน | เปลี่ยน `B` แล้ว counter เก่าถูกตีความใหม่เงียบ ๆ |
| **I17** | `cost_multi = ceil(K * c * (1 - d))` เสมอ พิมพ์แยกไม่ได้ | ราคา multi เข้ารหัสส่วนลดที่ไม่ได้ประกาศ |
| **I18** | `0.30 <= reach ของ floor pity <= 0.60` | floor pity ที่ไม่มีใครไปถึง หรือยิงทุกครั้งจนไร้ความหมาย |
| **I19** | เก็บ draw record ต่อผู้เล่นไม่ต่ำกว่า 90 วัน อ่านย้อนได้ต่อ pull | ตลาดที่บังคับเก็บ log (เช่นจีน) ตรวจสอบข้อพิพาทเรื่อง odds ย้อนหลังไม่ได้ |

> เลข **I16** เว้นว่างโดยตั้งใจในฉบับสาธารณะนี้ — เป็น invariant เฉพาะโปรเจกต์ที่ถูกถอดออกพร้อมชื่อตัวละคร/path/schema
> จริงตามที่ระบุไว้ในหัวเอกสาร ไม่ใช่เลขพิมพ์ตก

**I2 คือข้อที่คนมองข้ามบ่อยสุด** — เขียน "ผลรวมอยู่ภายใน tolerance" มันดูสมเหตุสมผลตอน pool 5 ตัว
แต่ tolerance ไม่โตตาม N พอ pool ถึง 50 ตัว มันพังเกือบทุกเคส วิธีที่ถูกคือให้สมาชิกตัวสุดท้าย
**ดูดเศษ** เข้าตัวเอง แล้วผลรวมเท่ากับ 1 โดยโครงสร้าง ไม่ใช่โดยการหวัง
