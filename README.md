# DialogWebView-Smali

ป้อบอัพเว็บเมื่อจิ้มปุ่ม

ใช้ ApkTool 2.0

ดาวน์โหลด

1. Decompile App.apk
2. คัดลอกโฟลเดอร์ com ไปใส่ในโฟลเดอร์ smali
3. เปิด AndroidManifest.xml แล้วหา <category android:name="android.intent.category.LAUNCHER" />
4. หา <activity android:name=" ที่อยู่ข้างบน <category android:name="android.intent.category.LAUNCHER" />
5. เปิดไฟล์ ที่ชื่อเดียวกับ <activity android:name="ตรงนี้" ......... > 

