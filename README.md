# 📶 Campus Wi-Fi Reporting & Monitoring System
**ระบบแจ้งปัญหาและติดตามสถานะ Wi-Fi มหาวิทยาลัย**

ระบบเว็บแอปพลิเคชันสำหรับอำนวยความสะดวกให้นิสิต บุคลากร และเจ้าหน้าที่ IT ในการแจ้งปัญหา ปรับปรุง และติดตามสถานะเครือข่าย Wi-Fi แบบ Real-time ภายในมหาวิทยาลัย

---

## 📌 คุณสมบัติหลักของระบบ (Key Features)

- **FR-01 Authentication (SSO):** รองรับการล็อกอินเข้าใช้งานผ่านบัญชีมหาวิทยาลัย (Student / Staff Account)[cite: 7, 9]
- **FR-02 Issue Reporting:** แบบฟอร์มแจ้งปัญหาอินเทอร์เน็ต สามารถระบุตึก ชั้น ประเภทปัญหา และแนบรูปภาพประกอบได้[cite: 7, 9]
- **FR-03 Ticket Management:** ระบบคิวงานสำหรับเจ้าหน้าที่ IT เพื่อกดรับเรื่อง และอัปเดตสถานะการแก้ไข (Pending -> In Progress -> Resolved)[cite: 7, 9]
- **FR-04 Network Status Map:** แสดงแผนที่และสถานะเครือข่ายแยกตามโซน/อาคาร (สีเขียว = ปกติ, สีเหลือง = หนาแน่น, สีแดง = มีปัญหา)[cite: 7, 9]
- **FR-05 Real-time Notification:** ส่งการแจ้งเตือนไปยังผู้แจ้งเมื่อปัญหาได้รับการแก้ไขเรียบร้อยแล้ว[cite: 7, 9]

---

## 📁 โครงสร้างโปรเจกต์ (Project Structure)

```text
campus-wifi-reporting-system/
├── README.md                    # เอกสารรายละเอียดโปรเจกต์และการแบ่งงาน[cite: 13]
├── docs/                        # เอกสารไดอะแกรมและภาพประกอบ (ใบงานที่ 1-3)[cite: 1, 13]
│   ├── .gitkeep
│   ├── use-case-diagram.png
│   ├── class-diagram.png
│   └── sequence-diagram.png
└── src/                         # ซอร์สโค้ดหลักของระบบ
    ├── controllers/             # Logic การทำงานของระบบ
    │   ├── adminController.js   # [047] จัดการคิวงาน IT
    │   ├── authController.js    # [045] จัดการการยืนยันตัวตน
    │   ├── networkController.js # [062] จัดการสถานะเครือข่ายและการแจ้งเตือน
    │   └── ticketController.js  # [030] จัดการฟอร์มแจ้งปัญหา
    ├── models/                  # โครงสร้างข้อมูล (Data Models)
    │   ├── Ticket.js            # โครงสร้างข้อมูลใบแจ้งซ่อม
    │   └── User.js              # โครงสร้างข้อมูลผู้ใช้งาน
    └── views/                   # หน้าจอแสดงผล (Frontend UI)
        ├── index.html           # หน้าแรก / หน้าแจ้งปัญหา
        ├── it-dashboard.html    # หน้าแดชบอร์ดสำหรับ IT
        └── report.html          # หน้าฟอร์มรายละเอียดรายงานปัญหา
