# webro
โอเค มาดูเป็น step-by-step แบบชัด ๆ เลย 📝


---

🔽 1. โหลดและแตกไฟล์สคริปต์

1. นำไฟล์ ro_scripts.zip เข้าไปใน Termux (ผ่าน cp, mv, หรือ wget ก็ได้)


2. แตกไฟล์:

unzip ro_scripts.zip -d ~/ro_scripts


3. เข้าโฟลเดอร์:

cd ~/ro_scripts


4. ให้สิทธิ์รัน:

chmod +x *.sh




---

⚙️ 2. ติดตั้งระบบพื้นฐาน

./install_base.sh

อัปเดต Termux

ติดตั้ง Ubuntu (proot-distro)

ลง dependency (gcc, cmake, mariadb, nginx, screen ฯลฯ)



---

🎮 3. ดาวน์โหลดและ build rAthena

./install_rathena.sh

จะโหลด rAthena ล่าสุดจาก GitHub

compile server (login, char, map)



---

🗄️ 4. ตั้งค่า Database

./setup_db.sh

start MariaDB

สร้าง database rathena

user: ragnarok / pass: password

import main.sql + logs.sql



---

📂 5. คัดลอก Config Pack

1. เอาไฟล์ rathena_configs_pack.zip (ที่เราสร้างไว้ก่อนหน้านี้) ไปวางใน HOME ของ Termux (~/)


2. รัน:

./copy_config.sh

จะคัดลอกเข้า Ubuntu และแตกไฟล์เข้า ~/rathena/

พร้อมตั้งสิทธิ์รัน start_server.sh, stop_server.sh, auto_all.sh, auto_stop.sh





---

🌐 6. ติดตั้ง roBrowser

./install_robrowser.sh

จะโหลด roBrowser เข้าไปใน /var/www/html/robrowser

ใช้ nginx เสิร์ฟหน้าเว็บ



---

🚀 7. วิธีรัน Server

รันแค่ rAthena

proot-distro login ubuntu -- ./rathena/start_server.sh

รันทุกอย่าง (MySQL + nginx + rAthena)

proot-distro login ubuntu -- ./rathena/auto_all.sh

ปิด

proot-distro login ubuntu -- ./rathena/stop_server.sh

หรือ

proot-distro login ubuntu -- ./rathena/auto_stop.sh


---

🌍 8. เข้าเกม

เปิด browser บนมือถือ/PC ที่อยู่ในวง LAN เดียวกัน

http://<IPมือถือ>:8080/robrowser/


---

อยากให้ผมเพิ่มสคริปต์ auto_update.sh ไว้ใน zip ด้วยเลยมั้ย — เวลาอยากอัปเดต rAthena แค่รันทีเดียวก็จบ?

