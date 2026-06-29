# devpool2569-portfolio

```text
devpool2569-portfolio
│
└── index.html
    ├── <head>
    │   ├── ตั้งค่าพื้นฐานของหน้าเว็บ (Meta Tags)
    │   ├── โหลด Google Fonts
    │   ├── กำหนด CSS Variables
    │   ├── กำหนด Theme (Light / Dark)
    │   └── กำหนด Responsive Layout
    │
    └── <body>
        ├── Weather Badge (สภาพอากาศอุดรธานี)   ← เพิ่มใหม่
        ├── ปุ่ม Toggle Theme
        ├── Hero Section
        │   ├── Avatar (คลิกได้)                ← อัปเดต
        │   └── Lightbox Popup                  ← เพิ่มใหม่
        ├── Section ทำไมถึงสมัคร
        ├── Section ทักษะ
        ├── Section ประสบการณ์
        ├── Section การศึกษา
        ├── JavaScript Logic
        └── Footer
```

## คำอธิบายโครงสร้าง

### devpool2569-portfolio

โฟลเดอร์หลักของโปรเจกต์ Portfolio สำหรับใช้สมัครเข้าร่วม DevPool 2569 โดยภายในมีไฟล์หลักคือ `index.html`

### index.html

ไฟล์หลักของเว็บไซต์แบบ Single Page Application (SPA) ที่รวมทั้ง HTML, CSS และ JavaScript ไว้ในไฟล์เดียว

---

### <head>

ส่วนที่ใช้เก็บข้อมูลและการตั้งค่าที่ผู้ใช้ไม่เห็นโดยตรง แต่จำเป็นต่อการทำงานของเว็บไซต์

#### ตั้งค่าพื้นฐานของหน้าเว็บ (Meta Tags)

ใช้กำหนดข้อมูลสำคัญ เช่น

* Encoding ของภาษา (`UTF-8`)
* Responsive สำหรับมือถือ
* Title ของเว็บไซต์
* Description สำหรับ Search Engine

ตัวอย่าง

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portfolio</title>
```

#### โหลด Google Fonts

ใช้ดึงฟอนต์จาก Google Fonts เพื่อให้เว็บไซต์มีรูปแบบตัวอักษรสวยงามและสม่ำเสมอ

ตัวอย่าง

```html
<link href="https://fonts.googleapis.com/..." rel="stylesheet">
```

#### กำหนด CSS Variables

กำหนดตัวแปรสีและค่าต่าง ๆ ส่วนกลาง

ตัวอย่าง

```css
:root {
  --bg: #ffffff;
  --text: #222222;
  --primary: #ff7a00;
}
```

ข้อดีคือเปลี่ยนสีทั้งเว็บไซต์ได้ง่ายเพียงแก้ค่าที่จุดเดียว

#### กำหนด Theme (Light / Dark)

สร้างชุดตัวแปรสีสำหรับ Light Mode และ Dark Mode

ตัวอย่าง

```css
[data-theme="dark"] {
  --bg: #0D1117;
  --text: #E6EDF3;
}
```

เมื่อ Theme เปลี่ยน สีทุกส่วนของเว็บจะเปลี่ยนตามทันที

#### กำหนด Responsive Layout

กำหนดรูปแบบการแสดงผลให้รองรับ

* Desktop
* Tablet
* Mobile

โดยใช้ Media Query

ตัวอย่าง

```css
@media (max-width: 768px) {
  ...
}
```

---

### <body>

ส่วนที่แสดงผลจริงบนหน้าจอให้ผู้ใช้งานเห็น

---

### Weather Badge *(เพิ่มใหม่)*

แสดงสภาพอากาศปัจจุบันของจังหวัดอุดรธานีแบบ Real-time มุมซ้ายบนของหน้าจอ

หน้าที่

* เรียก Open-Meteo API เมื่อโหลดหน้า (ไม่ต้องมี API Key)
* แปลงรหัส WMO Weather Code → emoji + คำอธิบายภาษาไทย
* แสดงอุณหภูมิ (°C) และสภาพอากาศ

ตัวอย่างที่แสดง

```text
🌧️ 33°C · ฝนปานกลาง · อุดรฯ
```

ออกแบบให้

* `position: fixed` — ค้างอยู่มุมซ้ายบนแม้ scroll หน้า
* ใช้ CSS Variables ชุดเดียวกับปุ่ม Toggle Theme — เปลี่ยนสีตาม Dark/Light Mode อัตโนมัติ
* Pill shape เหมือนปุ่ม Toggle Theme — ดูเข้าชุดกัน

API ที่ใช้

```text
https://api.open-meteo.com/v1/forecast
  ?latitude=17.41          ← อุดรธานี
  &longitude=102.79
  &current=temperature_2m,weathercode
  &timezone=Asia/Bangkok
```

---

### ปุ่ม Toggle Theme

ปุ่มสำหรับสลับ Light Mode และ Dark Mode มุมขวาบนของหน้าจอ

หน้าที่

* รับการคลิกจากผู้ใช้
* เรียก JavaScript
* เปลี่ยนค่า Theme
* บันทึกค่าลง `localStorage` — รีเฟรชหน้าแล้วจำธีมเดิมได้

ตัวอย่าง

```html
<button id="theme-toggle">
```

---

### Hero Section

ส่วนแรกของเว็บไซต์ใช้แนะนำตัวผู้สมัคร

ประกอบด้วย

* ชื่อ
* ตำแหน่งที่สมัคร
* รูปภาพ Avatar (คลิกเพื่อขยายได้)
* คำอธิบายสั้น ๆ

เป็นส่วนที่ผู้เข้าชมเห็นก่อนส่วนอื่นทั้งหมด

#### Avatar *(อัปเดต)*

รูปโปรไฟล์วงกลมขนาด 130×130px มีกรอบสีส้ม

* `cursor: zoom-in` — บอกผู้ใช้ว่าคลิกได้
* เมื่อคลิก → เปิด Lightbox แสดงรูปขนาดใหญ่

#### Lightbox Popup *(เพิ่มใหม่)*

ป๊อปอัพแสดงรูป Avatar ขนาดใหญ่ทับหน้าจอ

หน้าที่

* คลิก Avatar → เปิด Lightbox
* คลิกพื้นหลังสีดำ → ปิด Lightbox
* กดปุ่ม ✕ มุมขวาบนของรูป → ปิด Lightbox
* กด `Escape` บน Keyboard → ปิด Lightbox

ออกแบบให้

* `position: fixed` ครอบทั้งหน้าจอ พื้นหลัง `rgba(0,0,0,.85)` + `backdrop-filter: blur`
* ปุ่ม ✕ ใช้ `position: absolute` เทียบกับกล่องรูป — ลอยอยู่มุมขวาบนของรูปโดยตรง
* Animation `popIn` เมื่อเปิด — รูปขยายจาก 85% → 100%

---

### Section ทำไมถึงสมัคร

ใช้แสดงเหตุผลที่ต้องการเข้าร่วม DevPool ในรูปแบบ Accordion

ตัวอย่างเนื้อหา

* เป้าหมายในการพัฒนาตนเอง
* ความสนใจด้านเทคโนโลยี
* ประโยชน์ที่คาดว่าจะได้รับ

ช่วยให้คณะกรรมการเข้าใจแรงจูงใจของผู้สมัคร

---

### Section ทักษะ

แสดงความสามารถทางเทคนิคในรูปแบบ Grid Card

เช่น

* RPA / PowerAutomate
* Python
* Google Apps Script
* HTML / Web App
* GIS Survey
* SAP · SCS · WOM

---

### Section ประสบการณ์

รวบรวมประสบการณ์การทำงานและโครงการที่ผ่านมา แสดงในรูปแบบ Timeline

ตัวอย่าง

* เขียนเว็บแอพ / พัฒนานวัตกรรม (2567–ปัจจุบัน)
* ผู้ดูแลระบบ GIS / รับคำร้องขอใช้ไฟฟ้า (2563–2567)
* ผูกและสับเปลี่ยนมิเตอร์เข้าระบบ SAP (2557–2563)

---

### Section การศึกษา

แสดงประวัติการศึกษาในรูปแบบ Grid 2 คอลัมน์

เช่น

* ปวช. ไฟฟ้าและอิเล็กทรอนิกส์
* ปวส. เทคนิคคอมพิวเตอร์

---

### JavaScript Logic

ส่วนที่ควบคุมพฤติกรรมของเว็บไซต์ แบ่งเป็น 4 ส่วน

| ส่วน | หน้าที่ |
|---|---|
| Lightbox | เปิด/ปิดป๊อปอัพรูป Avatar |
| Theme Toggle | สลับ Dark/Light Mode + บันทึกลง localStorage |
| Accordion | เปิด/ปิดคำตอบในส่วน "ทำไมถึงสมัคร" |
| Scroll Fade-in | element ค่อย ๆ โผล่เมื่อ scroll ลงมาถึง |
| Weather Fetch | ดึงข้อมูลสภาพอากาศจาก Open-Meteo API |

---

### Footer

ส่วนท้ายของเว็บไซต์

ประกอบด้วย

* ชื่อ-สกุล
* โปรแกรม DevPool 2569
* สังกัด (การไฟฟ้าส่วนภูมิภาค)
* ลิงก์ portfolio-spnt.web.app

---

# ลำดับการทำงานของ Dark Mode

```text
ผู้ใช้กด Dark Mode
│
▼
JS: addEventListener('click')
│
├─ ตรวจจับการคลิกปุ่ม
│
├─ อ่านค่า data-theme ปัจจุบัน
│
├─ ถ้าเป็น light → เปลี่ยนเป็น dark
│
└─ ถ้าเป็น dark → เปลี่ยนเป็น light
│
▼
JS: setAttribute('data-theme', 'dark')
│
├─ เปลี่ยน Attribute ของแท็ก <html>
│
└─ ส่งผลให้ CSS Selector ตรวจพบการเปลี่ยนแปลง
│
▼
CSS: [data-theme="dark"]
│
├─ เปลี่ยน --bg
├─ เปลี่ยน --text
├─ เปลี่ยน --card
├─ เปลี่ยน --primary
└─ เปลี่ยนตัวแปรสีทั้งหมด
│
▼
Browser Render Engine
│
├─ คำนวณ CSS ใหม่
├─ สร้าง Layout ใหม่
└─ วาดหน้าจอใหม่
│
▼
Dark Mode แสดงผลทันที
```

---

# ลำดับการทำงานของ Lightbox *(เพิ่มใหม่)*

```text
ผู้ใช้คลิก Avatar
│
▼
JS: addEventListener('click') บน #avatar-btn
│
└─ lightbox.classList.add('show')
│
▼
CSS: #lightbox.show { display: flex }
│
└─ Lightbox โผล่ขึ้นทับหน้าจอ + animation popIn
│
▼
ผู้ใช้ปิด Lightbox (3 ทาง)
│
├─ คลิกพื้นหลังสีดำ  → e.target !== img → classList.remove('show')
├─ กดปุ่ม ✕          → classList.remove('show')
└─ กด Escape          → e.key === 'Escape' → classList.remove('show')
│
▼
CSS: #lightbox { display: none }
│
└─ Lightbox หายไป
```

---

# ลำดับการทำงานของ Weather Badge *(เพิ่มใหม่)*

```text
หน้าเว็บโหลด
│
▼
JS: IIFE fetchWeather() รันทันที
│
▼
fetch(Open-Meteo API)
│
├─ สำเร็จ
│   ├─ แปลง JSON → อ่าน temperature_2m และ weathercode
│   ├─ ค้นหา weathercode ในตาราง WMO → ได้ emoji + คำอธิบาย
│   └─ แสดงผล เช่น "🌧️ 33°C · ฝนปานกลาง · อุดรฯ"
│
└─ ล้มเหลว (ไม่มีเน็ต / API ล่ม)
    └─ แสดง "❓ โหลดไม่ได้"
```

## สรุปการไหลของระบบ

```text
ผู้ใช้
  │
  ├─► คลิกปุ่ม Theme ──► JS เปลี่ยน data-theme ──► CSS Variables เปลี่ยน ──► Browser Re-render
  │
  ├─► คลิก Avatar ──────► JS เพิ่ม .show ─────────► Lightbox แสดงผล
  │
  └─► โหลดหน้าเว็บ ─────► fetch Open-Meteo ────────► Weather Badge แสดงผล
```