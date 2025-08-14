# 🔌 ESP32 OLED Time Display + Web Relay Control

โปรเจกต์นี้ใช้ **ESP32 Dev Module (หรือ ESP32-C3)** ร่วมกับ **หน้าจอ OLED 128x64 (SSD1306)** เพื่อแสดงเวลาจาก NTP และควบคุมรีเลย์ 1 ช่องผ่านหน้าเว็บ พร้อมระบบจดจำสถานะเมื่อรีเซ็ตเครื่อง

---

## 📦 คุณสมบัติ

- ✅ แสดงเวลาและวันที่จาก NTP (โซนเวลา GMT+7)
- 🖥️ แสดงผลบน OLED SSD1306 แบบ centered
- 🔁 แสดงข้อความหัวจอสลับทุก 5 วินาที:
  - `Date & Time: Thailand`
  - `IP: xxx.xxx.xxx.xxx`
  - `Relay Status: ON/OFF`
- 🌐 มี Web Server สำหรับควบคุมรีเลย์ (ล็อกอินได้)
- 💾 จำค่าสถานะรีเลย์แม้หลังรีเซ็ต (ผ่าน Preferences)

---

## 🧰 อุปกรณ์ที่ใช้

- ESP32 Dev Module หรือ ESP32-C3 Pro Mini
- จอ OLED ขนาด 128x64 (I2C, SSD1306)
- Relay 1 ช่อง (ควบคุมด้วย GPIO)
- สายไฟ + แหล่งจ่ายไฟ 5V

---

## 🖼️ หน้าจอ OLED

```text
+----------------------------+
| Date & Time: Thailand     | ← ข้อความสลับ
|                            |
|          12:34:56         | ← เวลา
|                            |
|         14/08/2025         | ← วันที่
+----------------------------+
🌐 Web Interface
เข้า IP Address ของบอร์ดผ่าน browser

จะมีหน้าเว็บให้กดปุ่ม:

✅ Turn ON

❌ Turn OFF

ระบบมีล็อกอิน:
Username: admin
Password: 1234

🔧 วิธีใช้ / Upload โค้ด
เปิด Arduino IDE

เลือกบอร์ด ESP32 Dev Module

ติดตั้ง Library ต่อไปนี้ผ่าน Library Manager:

Adafruit SSD1306

Adafruit GFX

Preferences

ต่อ OLED ตาม I2C Pin:

SDA = 21

SCL = 22
(สามารถแก้ตามบอร์ดได้ใน Wire.begin();)

อัปโหลดโค้ดจากไฟล์ .ino

เปิด Serial Monitor → ดู IP แล้วใช้งานผ่าน browser

📝 การแก้ไขเพิ่มเติม
แก้ไข WiFi SSID/Password ที่บรรทัดนี้:

cpp
Copy
Edit
const char* ssid     = "xxxxxxxxx";
const char* password = "xxxxxxxxx";
แก้ไขพินรีเลย์:

cpp
Copy
Edit
#define RELAY_PIN 5
เปลี่ยน user/password login หน้าเว็บ:

cpp
Copy
Edit
const char* loginUser = "admin";
const char* loginPass = "1234";
📷 ตัวอย่างการใช้งาน
(แนะนำใส่รูปถ่ายการทำงานของ OLED และหน้าเว็บจาก browser)

🤝 License
MIT License — ใช้ฟรี ดัดแปลงได้ แชร์ต่อได้เต็มที่ 🚀

👨‍💻 ผู้จัดทำ
💡 พัฒนาโดย: [ใส่ชื่อของคุณที่นี่]

🛠️ ใช้ ChatGPT ช่วยในการจัดโครงสร้าง
