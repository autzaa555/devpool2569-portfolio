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
        ├── ปุ่ม Toggle Theme
        ├── Hero Section
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
:root{
  --bg:#ffffff;
  --text:#222222;
  --primary:#ff7a00;
}
```

ข้อดีคือเปลี่ยนสีทั้งเว็บไซต์ได้ง่ายเพียงแก้ค่าที่จุดเดียว

#### กำหนด Theme (Light / Dark)

สร้างชุดตัวแปรสีสำหรับ Light Mode และ Dark Mode

ตัวอย่าง

```css
[data-theme="dark"]{
  --bg:#0D1117;
  --text:#E6EDF3;
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
@media(max-width:768px){
  ...
}
```

---

### <body>

ส่วนที่แสดงผลจริงบนหน้าจอให้ผู้ใช้งานเห็น

---

### ปุ่ม Toggle Theme

ปุ่มสำหรับสลับ Light Mode และ Dark Mode

หน้าที่

* รับการคลิกจากผู้ใช้
* เรียก JavaScript
* เปลี่ยนค่า Theme

ตัวอย่าง

```html
<button id="theme-toggle">
```

---

### Hero Section

ส่วนแรกของเว็บไซต์

ใช้แนะนำตัวผู้สมัคร

ประกอบด้วย

* ชื่อ
* ตำแหน่งที่สมัคร
* รูปภาพ
* คำอธิบายสั้น ๆ

เป็นส่วนที่ผู้เข้าชมเห็นก่อนส่วนอื่นทั้งหมด

---

### Section ทำไมถึงสมัคร

ใช้แสดงเหตุผลที่ต้องการเข้าร่วม DevPool

ตัวอย่างเนื้อหา

* เป้าหมายในการพัฒนาตนเอง
* ความสนใจด้านเทคโนโลยี
* ประโยชน์ที่คาดว่าจะได้รับ

ช่วยให้คณะกรรมการเข้าใจแรงจูงใจของผู้สมัคร

---

### Section ทักษะ

แสดงความสามารถทางเทคนิค

เช่น

* HTML
* CSS
* JavaScript
* Firebase
* Google Apps Script
* Git
* SQL

อาจแสดงเป็น

* Card
* Badge
* Progress Bar

เพื่อให้อ่านง่าย

---

### Section ประสบการณ์

รวบรวมประสบการณ์การทำงานและโครงการที่ผ่านมา

ตัวอย่าง

* ระบบ Google Apps Script
* ระบบจัดการข้อมูล PEA
* งาน AI และ YOLO
* งาน Firebase

แสดงให้เห็นถึงความสามารถในการทำงานจริง

---

### Section การศึกษา

แสดงประวัติการศึกษา

เช่น

* วุฒิการศึกษา
* หลักสูตรอบรม
* Certificate

ช่วยยืนยันพื้นฐานความรู้ของผู้สมัคร

---

### JavaScript Logic

ส่วนที่ควบคุมพฤติกรรมของเว็บไซต์

ตัวอย่าง

* Theme Toggle
* Scroll Animation
* Event Handling
* Dynamic Content

ทำให้เว็บไซต์มีความโต้ตอบกับผู้ใช้

---

### Footer

ส่วนท้ายของเว็บไซต์

มักประกอบด้วย

* Email
* GitHub
* LinkedIn
* Copyright

ใช้เป็นช่องทางติดต่อเพิ่มเติม

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

## สรุปการไหลของระบบ

```text
ผู้ใช้
  │
  ▼
คลิกปุ่ม Theme
  │
  ▼
JavaScript Event
  │
  ▼
เปลี่ยนค่า data-theme
  │
  ▼
CSS Variables เปลี่ยนค่า
  │
  ▼
Browser Re-render
  │
  ▼
หน้าเว็บเปลี่ยนเป็น Dark Mode
```
