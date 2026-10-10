# Get INVOLVED! ม.1 - แบบฝึกหัดภาษาอังกฤษออนไลน์ (ทวพ. - TWP)
### เวอร์ชัน 2.0.0 (Account Authentication, Progressive E-Certificate & Google Sheets Sync)

เว็บแอปพลิเคชันแบบฝึกหัดภาษาอังกฤษออนไลน์ ระดับชั้นมัธยมศึกษาปีที่ 1 (ม.1) พัฒนาตามหลักสูตรหนังสือเรียน **Get INVOLVED!** โดย **บริษัท สำนักพิมพ์ ไทยวัฒนาพานิช จำกัด (TWP)** 
รองรับบทเรียน Unit 5 - Unit 8 ครบถ้วนตามใบงานและวิดีโอสรุปบทเรียน พร้อมระบบฐานข้อมูลนักเรียน (Email & Password Login), การเชื่อมต่อ Google Sheets สองทาง (Two-Way Sync), ระบบประวัติการเข้าเรียน (Login_Logs), ลูกเล่นการเผยชื่อบนเกียรติบัตรทีละส่วนตามความก้าวหน้า (Progressive Name Reveal E-Certificate) และระบบสื่อสารสองทางระหว่างนักเรียนกับคุณครู

---

## 🌟 ฟีเจอร์เด่นในระบบ

1. 🔐 **ระบบยืนยันตัวตนนักเรียน (Student Account Authentication)**:
   - ป้องกันคะแนนสับสนและไม่ต่อเนื่อง ด้วยระบบ Email และ Password
   - มีฐานข้อมูลนักเรียน 53 คนจากระบบทะเบียน และรองรับการนำเข้ารายชื่อเพิ่มเติมจากไฟล์ Excel (.xlsx / .csv)
   - เมื่อนักเรียนพิมพ์อีเมล ระบบจะจับคู่ชื่อและโรงเรียนขึ้นมาแสดงแบบ Real-time ทันที

2. 🏆 **เกียรติบัตรอิเล็กทรอนิกส์พร้อมลูกเล่น Progressive Name Reveal**:
   - ออกเกียรติบัตรความละเอียดสูง พร้อมรหัสกำกับเกียรติบัตร (Serial Number) และตราสัญลักษณ์ ทวพ. (TWP)
   - **ลูกเล่นพิเศษ (Progress Quest)**: ชื่อ-นามสกุลของนักเรียนบนเกียรติบัตรจะค่อยๆ ปรากฏทีละส่วน (25%, 50%, 75%, 100%) ตามสัดส่วนแบบฝึกหัดที่ทำเสร็จ เพื่อสร้างแรงจูงใจในการทำให้ครบทุกบทเรียน
   - สามารถดาวน์โหลดภาพความคมชัดสูง (PNG), พิมพ์ (Print) หรือกดส่งตรงเข้าอีเมลนักเรียนได้ทันที

3. ☁️ **การเชื่อมต่อ Google Sheets Web App ในตัว (Ready-to-use Backend)**:
   - ฝัง URL ระบบมาตรฐานไว้พร้อมใช้งานได้ทันที: `https://script.google.com/macros/s/AKfycbyma9twsGEiCaBO2AhwGQ8uGPpXNTxba4O3ivKhKRJ67GNJReZyW9VYKrWaVVKA7io8EQ/exec`
   - รองรับการเปลี่ยนไปใช้ Google Sheet ส่วนตัวของโรงเรียน และมีปุ่มกดรีเซ็ตกลับเป็น URL เริ่มต้นได้ตลอดเวลา
   - เชื่อมโยงฐานข้อมูลแผ่น `Name_base`, `Students_DB`, `Scores_Log`, `Certificates` และ `Login_Logs`

4. 🛡️ **ระบบรักษาความปลอดภัยสำหรับครู (Teacher PIN & Security)**:
   - ปิดซ่อนรหัสผ่านจากหน้าจอ UI อย่างปลอดภัย (รหัส PIN เริ่มต้นคือ `1234` และเปลี่ยนได้ในหน้า Dashboard)
   - แถบแจ้งเตือนและ Popup ต่างๆ มีปุ่มปิด `✕` และตั้งเวลานับถอยหลังปิดตัวเองอัตโนมัติภายใน 5 วินาที

5. 📱 **สถาปัตยกรรม Single Page Application (Zero-Build & GitHub Pages Ready)**:
   - ไม่ต้องติดตั้ง Node.js หรือรันคำสั่ง Build ใดๆ
   - มีไฟล์ `.nojekyll` และ `404.html` ครบถ้วน พร้อมเปิดใช้งานบน GitHub Pages ได้ทันที 100%

---

## 📁 โครงสร้างไฟล์สำหรับ Deploy ขึ้น GitHub

โฟลเดอร์สำหรับนำขึ้น GitHub (`deploy_github/`):

```
deploy_github/
├── .gitignore                   # กรองไฟล์ระบบและไฟล์ขยะออก
├── .nojekyll                    # ปิดการทำงานของ Jekyll บน GitHub Pages (สำคัญมาก)
├── 404.html                     # หน้าสำรองกรณีเข้าลิงก์ผิด พร้อม Redirect กลับหน้าแรก
├── Code.gs                      # โค้ด Google Apps Script v2.0 สำหรับวางใน Google Sheets
├── google-apps-script.js        # โค้ด Backend API รูปแบบ JavaScript
├── google-apps-script.txt       # โค้ด Backend API รูปแบบข้อความ (เปิดใน Notepad ได้)
├── index.html                   # ไฟล์เว็บแอปพลิเคชันหลัก (รวมหน้าฝึกหัด, เกียรติบัตร, ระบบครู)
├── README.md                    # คู่มือการติดตั้งและคำอธิบายระบบ
├── students_roster_template.csv # ไฟล์แม่แบบ CSV สำหรับนำเข้ารายชื่อนักเรียน
└── assets/
    ├── get-involved-logo.png    # โลโก้โครงการ Get INVOLVED!
    ├── students_roster_53.xlsx  # ฐานข้อมูลรายชื่อนักเรียน 53 คน (ไฟล์ Excel)
    ├── students_roster_template.csv # แม่แบบสำหรับโรงเรียน
    ├── twp-logo.png             # โลโก้สำนักพิมพ์ไทยวัฒนาพานิช (TWP)
    └── xlsx.full.min.js         # ไลบรารีอ่านไฟล์ Excel แบบออฟไลน์ (SheetJS)
```

---

## 🚀 ขั้นตอนการนำขึ้น GitHub Pages (Step-by-Step Guide)

คุณครูหรือผู้ดูแลระบบสามารถนำไฟล์ขึ้น GitHub Pages ได้ฟรี ง่ายๆ ใน 3 ขั้นตอน:

### วิธีที่ 1: อัปโหลดผ่านหน้าเว็บ GitHub (ไม่ต้องใช้โปรแกรม)

1. เข้าเว็บไซต์ [GitHub.com](https://github.com) และเข้าสู่ระบบบัญชีของท่าน
2. กดปุ่มสีเขียว **New** เพื่อสร้างคลังเก็บไฟล์ใหม่ (Repository):
   - **Repository name**: ตั้งชื่อเช่น `get-involved-m1`
   - เลือกสถานะเป็น **Public** (สาธารณะ)
   - ไม่ต้องติ๊กเพิ่ม README (เพราะในโฟลเดอร์มีให้แล้ว) แล้วกด **Create repository**
3. ในหน้าคลังที่สร้างขึ้น คลิกข้อความ **"uploading an existing file"**
4. ลากไฟล์และโฟลเดอร์ทั้งหมดจากโฟลเดอร์ `deploy_github/` (หรือแตกไฟล์จาก `deploy_github.zip`) มาวางลงในหน้าเว็บ
5. ด้านล่างพิมพ์ข้อความ Commit เช่น `Deploy Get Involved M.1 v2.0` แล้วกด **Commit changes**
6. **เปิดใช้งาน GitHub Pages**:
   - ไปที่แท็บ **Settings** ด้านบนของ Repository
   - เมนูด้านซ้ายเลือก **Pages**
   - ในหัวข้อ **Build and deployment > Branch**:
     - เลือก Branch: **`main`** (หรือ `master`)
     - เลือก Folder: **`/ (root)`**
     - กดปุ่ม **Save**
7. รอประมาณ 1-2 นาที GitHub จะแสดงแถบสีเขียวพร้อมลิงก์เว็บไซต์ เช่น:
   ```
   https://<your-username>.github.io/get-involved-m1/
   ```
   สามารถคัดลอกลิงก์นี้ส่งให้นักเรียนเข้าทำแบบฝึกหัดได้ทันทีบนมือถือ แท็บเล็ต และคอมพิวเตอร์!

---

### วิธีที่ 2: ใช้คำสั่ง Git (สำหรับผู้ใช้ Git CLI)

```bash
cd deploy_github
git init
git add .
git commit -m "Deploy Get INVOLVED M.1 Web App v2.0"
git branch -M main
git remote add origin https://github.com/<your-username>/get-involved-m1.git
git push -u origin main
```
จากนั้นไปที่แท็บ **Settings > Pages** และเลือก Branch **`main` / `/ (root)`** ตามขั้นตอนปกติ

---

## 🔧 ข้อมูลทางเทคนิค & คุณสมบัติการ Deploy

| หัวข้อ | รายละเอียดการตั้งค่า |
|---|---|
| **Architecture** | Single Page Application (HTML5, Vanilla JavaScript ES6, Tailwind CSS CDN) |
| **Hosting Compatibility** | GitHub Pages, Vercel, Netlify, Cloudflare Pages หรือ Web Hosting ทั่วไป |
| **Jekyll Processing** | บายพาสด้วยไฟล์ `.nojekyll` ใน Root Directory |
| **Offline Capability** | มีไลบรารี SheetJS (`xlsx.full.min.js`) ในตัว รองรับการอัปโหลด Excel แม้เน็ตช้า |
| **Database & Cloud** | Google Sheets & Google Apps Script Web App (JSONP / RESTful API) |
| **Asset Linking** | ใช้ Relative Path ทั้งหมด (`assets/...`) 100% ไม่หลุด 404 เมื่ออยู่บน Subpath |

---

**พัฒนาโดย**: โครงการพัฒนานวัตกรรมการเรียนรู้ดิจิทัล  
**บริษัท สำนักพิมพ์ ไทยวัฒนาพานิช จำกัด (TWP)** &copy; 2026 สงวนลิขสิทธิ์
