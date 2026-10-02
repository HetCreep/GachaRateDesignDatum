---
title: ที่มาจาก exemplar
---

## 4. ที่มาจาก exemplar — เกมจริง 6 เกม พร้อมแหล่ง

นี่คือส่วนที่ทำให้เอกสารนี้ต่างจาก "best practice" ทุกบรรทัดในกฎข้างบนมาจากพฤติกรรมที่วัดได้ของ
เกมที่เผยแพร่เรตของตัวเองไว้ ไม่ใช่จากความเห็น

![ตารางเปรียบเทียบ 6 เกม (Genshin, Honkai Star Rail, Arknights, FGO, Fire Emblem Heroes, Blue Archive) ต่อ 4 คุณสมบัติ: band rate คงที่, pool ขยับแทนการปรับ rate, duplicate จัดชั้นตามความหายาก, multi-pull ราคาต่อครั้งเท่ากันเป๊ะ (d=0) — เครื่องหมายถูกต่อช่องที่มีแหล่งอ้างอิงระบุ เส้นประต่อช่องที่ไม่มีข้อมูลระบุไว้](../../assets/g1-exemplar-comparison-matrix.svg)

*รูป — สรุปภาพรวมของตารางด้านล่าง ตัวเลขและแหล่งอ้างอิงจริงอยู่ในรายการ prose ต่อจากนี้ ถ้ารูปกับ
เนื้อหาขัดกัน ให้ยึดเนื้อหา*

### band rate เป็นค่าคงที่ ฟังก์ชันของ banner type เท่านั้น

- **Genshin** 0.600% นิ่งตอน roster โตจาก 5 → 8 ตัว
- **Honkai Star Rail** 0.600% / 1.600% / pity 90 เหมือนกันทุกหลักตั้งแต่ v1.5 (2023-11) ถึง v4.4
  (2026-08) ขณะที่ roster โตจาก ~9 → 70+
- **Arknights** 2% ตั้งแต่ภาพ disclosure วันเปิดตัวถึงโพสต์ EN 2026-04-28
- **FGO** 1% ต่อเนื่องสิบเอ็ดปี
- **Fire Emblem Heroes** 3%/3% ที่ 90 ตัว และ 3.00%/3.00% ที่ ~1,528 ตัว

**อ่านตรงนี้ให้ดี**: ห้าเกม ห้าสตูดิโอ ทุกเกมโรสเตอร์โตหลายเท่า **ไม่มีเกมไหนขยับ band rate เลย**
สิ่งที่ขยับคือ *ใครอยู่ใน pool*

### โรสเตอร์โต = pool membership ขยับ ไม่ใช่เรต

- **Arknights** ถอด 6★ 21 ตัวและ 5★ 37 ตัวออกจาก pool (2023-03-30) แทนที่จะขึ้นจาก 2%
- **HSR** แช่ permanent 5★ pool ไว้ที่ 7 ตัวเดิมสามปี และตรึง event pool ที่ N=8
- **Blue Archive** กัน Fest/Recollection/Archive ออกจาก 108 ตัว
- **FGO** curate pool ต่อ banner (18 non-pickup 5★ ทั้งที่มี 65)
- **FEH** ปลด hero จากแบนด์ 5★ ลง 4★

### เรตต่อตัวเป็นเลขคณิตที่ generate ไม่ใช่คนเขียน

- **Blue Archive**: featured 0.700000%, อีก 107 ตัวเท่ากันหมดที่ 0.021495% = (3.0−0.7)/107
  และ Nexon ประกาศทิศทางการ derive เอง — 「세부 확률은 소수점 7번째 자리에서 반올림한 수치이며,
  실제 합산 확률은 100%에 맞추어 적용됩니다」 (ปัดที่ทศนิยมที่ 7 แล้วบังคับผลรวมเป็น 100% พอดี)
- **FGO**: (1.000−0.700)/18 = 0.016
- **FEH**: ประกาศตรง ๆ ว่า "Heroes do not have individual drop rates"

### ผลรวมบังคับเป็น 1 พอดี + ประกาศกฎการปัดข้างตาราง

Blue Archive ทำ residual absorption ตรง ๆ ส่วน **FGO ประกาศตรงข้าม** —
「確率は小数第4位で切り捨てているため，合計値が100％にならないこともある」 (ตัดที่ทศนิยมที่ 4
ผลรวมจึงอาจไม่เท่ากับ 100%) สองทางนี้ต่างกันจริง เลือกทางไหนก็ได้ แต่ต้อง**ประกาศว่าเลือกทางไหน**

### pity เป็น counter นอก sampler บอกเป็นจำนวน pull เต็ม

Blue Archive เพดาน 2 ขั้น 100/200 point (100 = การันตี ★3, pickup 50% · 200 = การันตี pickup;
recruitment-charge มี 2 ชนิด (ปกติ กับ 限定) นับแยกกัน ไม่ใช้ร่วมกัน รีเซ็ตเมื่อได้ตัวเป้าหมายของแบน pickup ที่ใช้
charge ชนิดเดียวกันเท่านั้น (ตัว pickup ของแบนอื่นที่ได้ระหว่างสุ่มอีกแบน ไม่ทำให้รีเซ็ต) 「同種類の任意のピックアップ募集でピックアップ対象をお迎えした時のみ」 —
แบนจบไม่รีเซ็ต charge ยกไปแบนถัดไป 「それまでの「呼び出しチャージ」は引き継がれます」 —
เปลี่ยนจากระบบ gacha-point เดิม 2026-07-29, ประกาศที่ bluearchive.jp/news/newsJump/679) ·
FGO 330 step function แบน 1–329 · Arknights spark 300 contract แบบ deterministic · FEH 40-summon
free choice

### floor pity ของแบนด์รอง — มีทุกเกมที่มี 3 แบนด์ขึ้นไป

Genshin และ HSR รัน counter 90 pull ของแบนด์บน **และ** floor 10 pull ของแบนด์รอง ·
Blue Archive สลับตารางบน slot ที่ 10 · Arknights การันตี 5★ ใน 10 pull แรก

### multi-pull เป็น batch ของ UI ไม่มีเนื้อหาเชิงเศรษฐกิจ (`d = 0`)

Genshin 10-pull = 10 Fates เป๊ะ · HSR เรียกมันเองว่า "a pure UI convenience" ·
Arknights 6000 Orundum = 10 × 600 · Blue Archive 1200 Pyroxene = 10 × 120

**ไม่มีเกมไหนลดราคาหัวข่าวสำหรับ multi** FGO แถมใบที่ 11 และ FEH รัน ladder 5/4/4/4/3 (ซึ่งเป็นคนละ
เรื่องกับส่วนลด) ⇒ default ที่ถูกคือ `d = 0` ถ้าราคา multi ของคุณไม่เท่ากับ `K × c` เป๊ะ แปลว่าคุณมี
ส่วนลดซ่อนอยู่ที่ยังไม่ได้ประกาศ

### duplicate keyed ตาม rarity และ source-agnostic

Genshin เขียนคำต่อคำว่า "whether obtained in a wish, redeemed at the shop, or awarded by the game" ·
HSR ใช้ถ้อยคำเดียวกัน · ระดับตาม rarity: Blue Archive 30/5/1, FGO 90/50/30, Arknights 10/5→15/8

**ไม่มี exemplar ไหนให้ shard เท่ากันข้าม rarity**

### ประกาศทั้ง base และ delivered

Genshin พิมพ์คู่ 0.600% base / 1.600% consolidated ทุก banner · HSR เหมือนกัน

### ประกาศเรตต่อตัวละคร ไม่ใช่แค่ band %

Blue Archive 0.021495% ต่อคน (ตามกฎหมายเกาหลี) · FGO 0.016% ต่อใบ ตั้งแต่ 2018-04-04
(เพราะ Apple App Store Review Guidelines 2017) · FEH เปิด "Details" ให้ผู้เล่นนับเอง

### display ต้อง generate จากตารางที่ sampler อ่าน — ทุก exemplar เป็น *คำเตือน* ไม่ใช่แบบอย่าง

- **Genshin EN** ทำคำว่า "promotional" หล่นจนพิมพ์ประโยคผิดบนหน้าที่ผูกกับกฎหมาย
- **Blue Archive** tutorial รันเรต 2.5% ค้างอยู่ **สิบสองเดือน** หลังยกทั้งเกมเป็น 3% ต้อง patch แยก
- **Arknights** เผยแพร่ disclosure เป็น PNG ที่ทำด้วยมือ
- **FGO** เป็นเคสบวกเคสเดียว — เศษที่พิมพ์เปลี่ยนตาม pool size แบบเลขคณิต ซึ่งเป็นพฤติกรรมของ generator

**สี่ในห้าเกมใหญ่เคยพลาดเรื่องเดียวกัน: เลขที่โชว์กับเลขที่สุ่มไม่ใช่แถวเดียวกัน**

### แหล่งอ้างอิงหลัก (สาธารณะทั้งหมด)

```
Genshin        gs.hoyoverse.com/static/hk4e-official-gacha-probability-fe/index.html?lang=en-us
               webstatic.mihoyo.com/hk4e/gacha_info/... (JSON ต่อ banner)
HSR            operation-webstatic.hoyoverse.com/gacha_info/hkrpg/... (JSON ต่อ banner)
Arknights      ak.hypergryph.com/news/6273 · ak.hypergryph.com/news/2023033352.html
               web.hycdn.cn/arknights/official/upload/images/20190501/... (PNG disclosure)
Blue Archive   forum.nexon.com/bluearchive/board_view?board=4606&thread=2480089 · m.nexon.com/probability/7717
               bluearchive.jp/news/newsJump/229 · /344 · /624 · /680 (ประกาศ 7/29) · /679 (เลขกลไกจริง)
FGO            4gamer.net/games/266/G026651/20180404124/
               news.fate-go.jp/info/servant_coin/
               nlab.itmedia.co.jp/nl/articles/1804/04/news130.html
FEH            new-guide.fire-emblem-heroes.com/en-US/feh-2020.html · /feh-3020.html
               feheroes.fandom.com/wiki/Summon
```

### compliance checklist ต่อ jurisdiction — invariant ข้อไหนตอบกฎ/policy ข้อไหน

revalidate ทุก 30 วัน หรือทันทีที่มี amendment ใหม่ประกาศ (regulatory surface เปลี่ยนเร็ว)

| กฎ/policy | มีผลตั้งแต่ | ข้อบังคับหลัก | invariant ที่ตอบโจทย์ |
| --- | --- | --- | --- |
| Korea Game Industry Promotion Act | 2024-03-22 | แสดง probability บนหน้าซื้อในเกมจริง ถ้าไม่เปิดเผยหรือแสดง probability เท็จ รัฐมนตรีอาจออกคำสั่งแก้ไขตาม [Article 38(9)](https://www.law.go.kr/법령/게임산업진흥에관한법률/제38조) และเฉพาะผู้ไม่ปฏิบัติตามคำสั่งนั้นจึงมีโทษตาม [Article 45](https://www.law.go.kr/법령/게임산업진흥에관한법률/제45조) จำคุกไม่เกิน 2 ปี หรือปรับไม่เกิน ₩20M | I5c, I8 |
| China Ministry of Culture Notice | 2017-05-01 | เผยแพร่ probability + เก็บ draw log ≥90 วัน | I5c, **I19** |
| Apple App Store Guideline 3.1.1 | 2017-12 | disclose odds ก่อนผู้เล่นกดซื้อ ไม่ใช่แค่มีตารางอยู่ที่ไหนสักที่ | I8 |
| Google Play Developer Policy (loot box) | 2019-05 | เงื่อนไขเดียวกับ Apple | I8 |

หมายเหตุ (2026-09): ร่างแก้ไขเพิ่มเติมของ ส.ส. Kim Sung-hoe (เสนอ 2025-12-23, เพิ่มโทษปรับสูงสุด 3%
ของยอดขาย/₩1B) ยังอยู่ระหว่างพิจารณาชั้นกรรมาธิการ (ทบทวนถึง ก.พ. 2026, กระทรวงผู้รับผิดชอบยังมีท่าที
ระมัดระวัง) — **ยังไม่บังคับใช้** แยกจากการแก้ไขที่มีผลบังคับแล้วข้างต้น
