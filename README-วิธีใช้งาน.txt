วิธีใช้งาน PWA Dashboard

ไฟล์ในโฟลเดอร์นี้:
1. index.html = หน้าแอปหลัก รวม Finance Planner + Lineman Tracker
2. manifest.webmanifest = ตั้งค่าชื่อแอป ไอคอน และโหมด standalone
3. service-worker.js = ช่วยให้ browser มองเป็น PWA และ cache ไฟล์
4. icons/icon-192.png และ icons/icon-512.png = ไอคอนแอป

วิธีเอาขึ้น GitHub Pages:
1. เข้า GitHub แล้วสร้าง repository ใหม่ เช่น my-dashboard
2. Upload ไฟล์ทั้งหมดในโฟลเดอร์นี้ไปไว้ระดับบนสุดของ repository
   - index.html ต้องอยู่หน้าแรกสุด ไม่อยู่ใน folder ซ้อน
   - manifest.webmanifest ต้องอยู่ข้าง index.html
   - service-worker.js ต้องอยู่ข้าง index.html
   - folder icons ต้องอยู่ข้าง index.html
3. ไปที่ Settings > Pages
4. Source เลือก Deploy from a branch
5. Branch เลือก main และ /root แล้วกด Save
6. รอ GitHub สร้าง URL ให้ เช่น https://username.github.io/my-dashboard/

วิธีติดตั้งบนมือถือ:
Android Chrome:
1. เปิด URL จาก GitHub Pages
2. กดเมนู ⋮
3. เลือก Add to Home Screen หรือ Install app

iPhone Safari:
1. เปิด URL จาก Safari
2. กด Share
3. เลือก Add to Home Screen

ข้อจำกัด:
- เวอร์ชันนี้ทำให้ดูเหมือนแอปและเปิดจาก Home Screen ได้
- ข้อมูลยังเก็บใน localStorage ของเครื่องนั้น ๆ
- ถ้าต้องการ sync ข้อมูลข้ามคอม/มือถือ ต้องเพิ่ม Firebase หรือ Supabase ต่อ
