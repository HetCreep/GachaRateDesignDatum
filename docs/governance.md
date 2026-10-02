---
title: Governance
---

ใครตัดสินใจเปลี่ยนค่าได้ และเปลี่ยนอย่างไร — รวบรวมจากกฎที่ประกาศไว้ในเอกสารเอง ไม่ใช่กฎใหม่

- **ทุกค่า BASE ต้อง ratify ทีละข้อกับเจ้าของโปรเจกต์** ผ่าน adversarial review 3 มุม ไม่ใช่เลือกคนเดียว
- **invariant ทุกข้อต้องรันเป็น automated test ใน CI** ทุก commit ที่แตะ BASE value — checklist มือเป็นแค่ fallback
- **BASE value เปลี่ยนทุกครั้งต้องบันทึกใน changelog** ที่ [CHANGELOG.md](https://github.com/HetCreep/GachaRateDesignDatum/blob/main/CHANGELOG.md) ของ repository พร้อมเลขเวอร์ชันใหม่
- **ค่าที่อิงข้อมูลภายนอก (ค่าแรง, compliance checklist) ต้อง revalidate ตาม cadence ที่ระบุ** — ค่าแรงทุกต้นปี กฎ/policy ทุก 30 วันหรือทันทีที่มี amendment
- **shard/ladder เป็น base อิสระ ไม่ derive จาก band rate** โดยตั้งใจ — กันไม่ให้การ re-ratify band rate กระทบเศรษฐกิจ shard เงียบ ๆ
