วิธีเปิด Firebase Cloud Sync

1) เข้า https://console.firebase.google.com
2) Create project ใหม่ เช่น dashboard-finance
3) Project Overview > กดไอคอน Web </> > Register app
4) Copy firebaseConfig มาใส่ใน index.html แทนค่า PASTE_...

5) เปิด Authentication
   Build > Authentication > Get started > Sign-in method
   Enable: Google
   Authorized domains ต้องมี:
   - localhost (มีให้ปกติ)
   - poroboy.github.io

6) เปิด Firestore Database
   Build > Firestore Database > Create database
   เลือก Production mode หรือ Test mode ก็ได้ แต่แนะนำ Production แล้วใส่ Rules นี้:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /dashboardSync/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}

7) Upload index.html ใหม่ขึ้น GitHub repo เดิม แล้ว commit
8) เปิดแอปใหม่ กด Sign in ด้วย Google
9) เมื่อใส่/แก้ข้อมูล แอปจะ auto-save ขึ้น Firestore ทุกประมาณ 1-2 วินาที

หมายเหตุ:
- ข้อมูลเดิมในเครื่องแรกจะถูกอัปโหลดไป cloud หลัง Sign in ครั้งแรก
- ถ้ามีข้อมูลใน cloud อยู่แล้ว เครื่องใหม่จะโหลดข้อมูลจาก cloud ลงมาให้


V4 note: เพิ่ม bottom padding สำหรับหน้า Finance บนมือถือ เพื่อไม่ให้รายการรายจ่ายติดขอบล่างจอ/PWA safe area.
