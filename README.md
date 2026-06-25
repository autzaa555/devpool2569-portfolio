# devpool2569-portfolio



index.html
├── <head>        → ตั้งค่าพื้นฐาน + โหลดฟอนต์ + CSS ทั้งหมด
└── <body>        → เนื้อหาที่คนเห็น + JavaScript ทั้งหมด
    ├── ปุ่ม toggle ธีม (มุมขวาบน)
    ├── section hero (หน้าแรก)
    ├── section ทำไมถึงสมัคร
    ├── section ทักษะ
    ├── section ประสบการณ์
    ├── section การศึกษา
    └── footer



    ผู้ใช้กด Dark Mode
    │
    ▼
JS: addEventListener('click')
    │  อ่านธีมปัจจุบันจาก data-theme
    │  สลับเป็นธีมตรงข้าม
    ▼
JS: setAttribute('data-theme', 'dark')
    │  เปลี่ยน attribute บน <html>
    ▼
CSS: [data-theme="dark"] { --bg: #0D1117 ... }
    │  ตัวแปรสีเปลี่ยนทั้งหมด
    ▼
เบราว์เซอร์ render สีใหม่ทั้งหน้าทันที ✅
