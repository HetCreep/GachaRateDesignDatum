# Changelog

All notable changes to `GACHA-RATE-DESIGN-LOCK-PUBLIC.md` are documented here. Format follows
[Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/); versions follow
[Semantic Versioning](https://semver.org/). A released entry is immutable—never edited after
the fact; a correction gets a new entry. This is this changelog's own rule.

**This file is the canonical, type-classified history.** The changelog sections inside
`GACHA-RATE-DESIGN-LOCK-PUBLIC.md` and `docs/README.md` are kept for readers of those single-file
surfaces (the core doc and the GitBook page render standalone) and are frozen as of the v1.1.2 entry
below—a future correction is recorded HERE first; the two in-document copies are not hand-updated
in parallel going forward. This is a relocation of where new entries land, not a removal of what
already exists in either surface.

Entry wording below is carried verbatim from the two source sections, unclassified prose regrouped
under Keep a Changelog's type headings — nothing was reworded. The one deliberate addition is the
**`(เฉพาะหน้า docs/)`** qualifier on two entries: the two source sections' histories differ by exactly
those two items (present on `docs/README.md` only), and merging them into one file without marking
which surface an entry applies to would state something false of the other surface.

## [Unreleased]

### Fixed
- Korea compliance row: nondisclosure or false probability information may lead to a ministerial
  corrective order under Article 38(9); Article 45 penalties apply only to failure to comply with
  that order. Added official statutory links in both the core document and `docs/explanation/exemplar.md`.

## [1.1.5] - 2026-10-01

### Changed
- Blue Archive §4 pity row, the Thai wording of the reset clause: it now says the charge resets
  only on obtaining the pickup target of a pickup banner that uses the same charge kind, and that a
  pickup unit of another banner won while pulling a different banner does not reset it. The
  Japanese quote beside it already said this; the Thai had read as "any pickup unit of that kind".
  The Japanese, the numbers, the dates and the source are unchanged. Applied identically to
  `GACHA-RATE-DESIGN-LOCK-PUBLIC.md` and `docs/explanation/exemplar.md`.
- The 1.1.3 and 1.1.4 entries lost their internal tracking references and two quoted remarks before
  this repository became public. No claim, number, date or source changed. This is the one recorded
  exception to the immutability rule above, which stands for claims.

## [1.1.4] - 2026-09-25

### Changed
- Blue Archive §4 pity row, reset scope widened to the two facts `/679` states and the row omitted:
  the charge resets only on obtaining the pickup of the SAME charge kind (the normal and 限定
  charges are counted separately, not shared), and a banner ending does NOT reset it (the charge
  carries into the next pickup). Source Japanese quoted verbatim in the row. No number changed.
  Applied identically to `GACHA-RATE-DESIGN-LOCK-PUBLIC.md` and `docs/explanation/exemplar.md`.
- (เฉพาะหน้า `docs/`) `docs/README.md`'s frozen changelog list now says where it stops (v1.1.2) and
  that later versions live in the source's `CHANGELOG.md`, which the site does not publish.

## [1.1.3] - 2026-09-04

### Fixed
- Blue Archive §4 pity-row mechanism corrected: the old single-stage "gacha-point เพดาน 200"
  description replaced with the real recruitment-charge system (100 = guaranteed ★3 with the
  pickup at 50%; 200 = guaranteed pickup; resets only on obtaining the pickup), applied
  identically to `GACHA-RATE-DESIGN-LOCK-PUBLIC.md` and `docs/explanation/exemplar.md`.
- Blue Archive mechanism citation corrected from `bluearchive.jp/news/newsJump/680` (the 7/29
  maintenance notice, which only announces the renewal and names its two terms) to `/679` (the
  linked notice actually carrying the mechanism's numbers). `/680` stays in the source
  register as the announcing notice; both `/680` and `/679` are now listed there with their roles
  distinguished.

### Added
- G-1 (the 6-game exemplar comparison figure) embedded in the `docs/` split at
  `docs/explanation/exemplar.md`, matching its existing placement in the core doc — previously
  core-only, so the published surface never carried it.
- G-2 (the band-rate distribution donut) embedded on both surfaces at §6's band-rate table,
  light/dark tone-matched via `<picture>` per the shared two-tone dialect.

## [1.1.2] - 2026-09-02

### Fixed
- ลิงก์ Blue Archive `m.nexon.com/probability/7716` (ตายแล้ว) → `forum.nexon.com/bluearchive`
  board 4606 thread 2480089 (2026-08-04, ยืนยันข้อความปัดเศษทศนิยมตำแหน่งที่ 7 เดิม)
- แถว Korea Game Industry Promotion Act — เดิมปนกันระหว่างการแก้ไขที่มีผลบังคับแล้ว (2025-08-01)
  กับร่างกฎหมายเพิ่มโทษของ ส.ส. Kim Sung-hoe (เสนอ 2025-12-23) ที่ยังอยู่ชั้นกรรมาธิการ ไม่บังคับใช้ —
  แยกสองเรื่องออกจากกันชัดเจน
- (เฉพาะหน้า `docs/`) ซิงก์ v1.1.1 ของ core มาที่หน้านี้ (หน้านี้ค้างเลข 9 เกม อยู่หนึ่งสัปดาห์)

## [1.1.1] - 2026-08-27

### Fixed
- จำนวนเกม exemplar 9 → 6 ใน intro และหัวข้อ §4 ให้ตรงรายการแหล่งอ้างอิงจริง ("9" เดิมหลุดมาจาก
  "9 จุด" ข้อมูลราคาใน §5 ซึ่งสร้างจาก 6 เกมเดิม — ตาราง §5 ไม่เปลี่ยน)

## [1.1.0] - 2026-08-13

### Added
- I19 (draw record retention)
- compliance checklist ต่อ jurisdiction (§4)
- revalidate cadence สำหรับค่าแรง (§5)
- หมายเหตุ I16
- เลขเวอร์ชัน/changelog นี้
- (เฉพาะหน้า `docs/`) จัดโครงสร้างใหม่เป็นหลายหน้า (Reference/Explanation/Guides/Governance/
  Contributing/License)

### Changed
- CI-gate rule ชัดเจน (§3)

## [1.0.0]

ฉบับสาธารณะแรก (ถอดข้อมูลเฉพาะโปรเจกต์ออก). *ไม่มีวันที่บันทึกไว้ในต้นฉบับ — ไม่เติมวันที่ขึ้นมาเอง.*
