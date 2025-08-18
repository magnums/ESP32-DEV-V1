📟 ESP32 Web Relay Scheduler + OLED Display

ควบคุมรีเลย์ผ่าน WiFi พร้อมตั้งเวลาทำงานได้สูงสุด 3 รอบต่อวัน แสดงสถานะผ่านหน้าจอ OLED และมีระบบกดปุ่มรีเซ็ต WiFi

✅ Features

✅ ควบคุมรีเลย์ผ่านหน้าเว็บ (เปิด / ปิด)

🕒 ตั้งเวลาเปิด-ปิดอัตโนมัติได้ 3 รอบ/วัน

📺 แสดงผล OLED 128x64 (เวลา / IP / สถานะรีเลย์)

🌐 ใช้ WiFiManager สำหรับตั้งค่า WiFi ผ่าน AP

🧹 ปุ่มล้าง WiFi (กดค้าง 5 วิ ที่ GPIO 4)

🧼 ปุ่มล้างตารางเวลาในหน้าเว็บ

🔐 มีระบบล็อกอิน (admin / 1234)

📝 เก็บสถานะรีเลย์ และตารางเวลาไว้ใน Flash (Preferences)

⚙️ Hardware ที่รองรับ

ESP32 Dev Module (เช่น ESP32 DevKit v1)

OLED Display 128x64 I2C (Address: 0x3C)

Relay Module 1 ช่อง

ปุ่มกด (สำหรับ Reset WiFi)

🖥️ Web Interface

/ — ควบคุมรีเลย์ (ON / OFF)

/schedule — ตั้งเวลาทำงาน 3 รอบ

/clear_schedule — ล้างเวลาที่ตั้งไว้

/resetwifi — ล้าง WiFi แล้วเข้า AP Mode

/reboot — รีบูตบอร์ด

🧾 ขาเชื่อมต่อ (ESP32 Dev v1)
รายการ	GPIO	หมายเหตุ
Relay	5	เปิด HIGH, ปิด LOW
OLED SDA	21	
OLED SCL	22	
ปุ่ม Reset WiFi	4	กดค้าง 5 วิเพื่อล้าง WiFi

หมายเหตุ: ถ้าใช้ ESP32-C3 Pro Mini ให้ใช้ SDA = 8, SCL = 9

📦 Libraries ที่ต้องใช้

ติดตั้งผ่าน Library Manager:

WiFiManager by tzapu

Adafruit SSD1306

Adafruit GFX

Preferences (built-in)

WebServer (built-in)

🧪 การใช้งาน

อัปโหลดโค้ดไปยัง ESP32

หากยังไม่เคยเชื่อม WiFi:

บอร์ดจะเข้าสู่โหมด AP Mode

เชื่อมต่อ WiFi ชื่อ ESP32-SETUP

เปิดเบราว์เซอร์ไปที่ 192.168.4.1

เลือก WiFi แล้วใส่รหัสผ่าน

จากนั้นเปิดหน้าเว็บ:

ไปยัง http://<IP_ADDRESS>

Login ด้วย admin / 1234

ควบคุมหรือจัดการเวลาเปิด-ปิดได้เลย

🧹 ปุ่ม Reset WiFi

ต่อปุ่มกดระหว่าง GPIO 4 กับ GND

กดค้าง 5 วินาที จะล้าง WiFi และเข้า AP Mode ใหม่อัตโนมัติ

📷 ตัวอย่างหน้าจอ (เว็บ)

ปุ่มเปิด/ปิดรีเลย์

หน้าตั้งเวลา

ปุ่มล้างเวลา

ปุ่ม Reset WiFi และ Reboot

💡 ข้อแนะนำเพิ่มเติม

สามารถขยายตารางเวลามากกว่า 3 รอบได้โดยเพิ่ม schedules[]

เพิ่มระบบ OTA หรือ MQTT ได้หากต้องการควบคุมระยะไกล

ระบบเวลาพื้นฐานจาก NTP แต่ไม่มี RTC สำรองเมื่อไม่มีเน็ต

📜 License

MIT License — ใช้ได้ฟรี ปรับแต่งได้ตามสะดวก
