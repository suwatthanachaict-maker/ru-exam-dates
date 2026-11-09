# Ramkhamhaeng University Exam Dates

เว็บวางแผนวันสอบวิชานิติศาสตร์ ม.รามคำแหง: เลือกวิชาจากปฏิทินสอบ รวมหน่วยกิตรอบปกติกับรอบซ่อม เช็กวันชน วางแผนจนจบ คิดเกรด และดาวน์โหลดวันสอบเป็นไฟล์ .ics

- `index.html` หน้าเว็บ
- `app.js` โค้ดและข้อมูลตารางสอบ / รายวิชา
- `firebase-config.js` ใส่ค่าตั้งค่า Firebase เพื่อเปิดระบบเข้าสู่ระบบด้วย Google (ถ้าเว้นว่าง เว็บจะเก็บแผนไว้ในเบราว์เซอร์)

## Firestore security rules

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{uid} {
      allow read, write: if request.auth != null && request.auth.uid == uid;
    }
  }
}
```
