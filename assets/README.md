# assets/

รูปทั้งหมดถูกจัดเข้าโฟลเดอร์ตามสตูดิโอแล้ว และเชื่อมเข้า `index.html` เรียบร้อย
เว็บลองโหลดตามลำดับ `.jpg` -> `.jpeg` -> `.png` -> `.webp` -> `.svg` (placeholder)
ถ้าไม่เจอไฟล์เลย จะถอยไปใช้พื้นไล่สี + ไอคอนเส้นแทน (หน้าไม่พัง)

## โครงสร้าง

```
assets/
├── bg/                          ภาพพื้นหลัง (หรี่จาง ๆ อยู่ข้างหลัง)
│   ├── galaxy.jpg               พื้นหลังกาแล็กซี่ส่วนหัว (เฟดลงหาตาราง)
│   ├── cycling.jpg              พื้นหลังตาราง Cycling Studio
│   ├── rangsit.jpg              พื้นหลังตาราง Studio 1
│   ├── bangna-pilates.jpg       พื้นหลังตาราง Pilates Studio
│   ├── bangna.jpg               สำรอง (ยังไม่ถูกใช้)
│   └── vibhavadi.jpg            สำรอง (ยังไม่ถูกใช้)
└── images/
    ├── cycling/    cycling.jpg  rpm.jpg
    ├── studio1/    yoga-basic  yoga  yoga-balance-power  body-combat  body-pump
    │               galaxy-fly  zumba  easy-step  easy-move  intermediate-step
    │               kid-bootcamp  galaxy-dance  retro-dance
    ├── pilates/    basic  beginner  flexible  aag  strength  power
    └── _library/   รูปคลาสที่ยังไม่มีในตาราง เก็บไว้ใช้ทีหลัง
```

## การจับคู่รูป (ทำไปแล้ว)

| คลาสในตาราง | ไฟล์เดิม | ไฟล์ใหม่ |
|---|---|---|
| CYCLING | cycling.jpg | cycling/cycling.jpg |
| RPM | rpm.jpg | cycling/rpm.jpg |
| YOGA BASIC | yoga_basic.jpg | studio1/yoga-basic.jpg |
| YOGA | yoga.jpg | studio1/yoga.jpg |
| YOGA BALANCE & POWER | yoga_balance.jpg | studio1/yoga-balance-power.jpg |
| BODY COMBAT | bodycombat.jpg | studio1/body-combat.jpg |
| BODY PUMP | bodypump.jpg | studio1/body-pump.jpg |
| GALAXY FLY | yoga_fly.jpg | studio1/galaxy-fly.jpg |
| ZUMBA | zumba.jpg | studio1/zumba.jpg |
| EASY STEP | easystep.jpg | studio1/easy-step.jpg |
| EASY MOVE | aerobic.jpg | studio1/easy-move.jpg |
| INTERMEDIATE STEP | intermediatestep.jpg | studio1/intermediate-step.jpg |
| KID BOOTCAMP | kidbootcamp.jpg | studio1/kid-bootcamp.jpg |
| GALAXY DANCE | galaxydance.jpg | studio1/galaxy-dance.jpg |
| RETRO DANCE | retrodance.jpg | studio1/retro-dance.jpg |
| BASIC / BEGINNER / FLEXIBLE / AAG / STRENGTH / POWER | ชื่อเดิม | pilates/ (ชื่อเดิม) |

> **EASY MOVE** ไม่มีไฟล์ชื่อตรง ใช้ `aerobic.jpg` แทน — ถ้ามีรูปที่ตรงกว่า วางทับได้ที่ `studio1/easy-move.jpg`

## รูปใน _library (ยังไม่ได้ใช้)
aerobicball, bodybalance, bodyweight, boxing, cardioboxing, coverdance, elasticband,
fitball, galaxyaqua, galaxytour, hiit, kpopdance, pilatesmat, qigong, stretching,
tabata, tibetansound, yoga_advance, yoga_gentleflow, yoga_insideflow, yoga_vinyasa

ถ้าเพิ่มคลาสใหม่ในตาราง ให้ย้ายรูปจาก `_library/` ไปโฟลเดอร์สตูดิโอ แล้วเปลี่ยนชื่อให้ตรง slug

## กฎการตั้งชื่อ
ชื่อไฟล์ = ชื่อคลาสตัวพิมพ์เล็ก ตัด `&` ออก แทนช่องว่างด้วย `-`
เช่น `YOGA BALANCE & POWER` -> `yoga-balance-power.jpg`

อยากใช้รูปเฉพาะคาบ (ไม่ใช้รูปกลางของคลาส) ใส่ชื่อไฟล์เป็นพารามิเตอร์ที่ 4 ของ `c()` ใน `index.html`:
`c('BODY PUMP','BALL','17:00 - 17:50','body-pump-ball')`

## เปลี่ยนพื้นหลังตาราง
แก้ค่า `bg:` ของแต่ละสตูดิโอใน `index.html` เช่น `bg:'assets/bg/vibhavadi.jpg'`
ความจาง/ความสว่างปรับที่ CSS คลาส `.boardbg` (`opacity` ปัจจุบัน `.20`)

## เปิดดูเว็บ
ดับเบิลคลิก `index.html` หรือรัน local server แล้วเปิด http://localhost:8000
