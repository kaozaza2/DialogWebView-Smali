# DialogWebView-Smali

ป้อบอัพเว็บเมื่อจิ้มปุ่ม

![alt text](https://raw.githubusercontent.com/kaozaza2/DialogWebView-Smali/master/Screenshots/01.gif)

ใช้ ApkTool 2.0

ดาวน์โหลด

1. Decompile App.apk
2. คัดลอกโฟลเดอร์ com ไปใส่ในโฟลเดอร์ smali
3. เปิด AndroidManifest.xml แล้วหา <category android:name="android.intent.category.LAUNCHER" />
4. หา <activity android:name=" ที่อยู่ข้างบน <category android:name="android.intent.category.LAUNCHER" />
5. เปิดไฟล์ ที่ชื่อเดียวกับ <activity android:name="ตรงนี้" ......... > 
6. ค้นหา #virtual methods แล้วก้อบโค้ดด้านล่างไปใส่ขั้งล่าง  #virtual methods
```smali
.method public popView(Landroid/view/View;)V
    .locals 0
    .param p1, "v"    # Landroid/view/View;

    .prologue
    invoke-static {p1}, Lcom/paper/PopupWebView/PopView;->PopView(Landroid/view/View;)V

    return-void
.end method
```
7. เป็ดไฟล์ com/paper/PopupWebView/PopView.smali
8. หา http://www.google.com แล้วแก้เป็นเว็บที่จะเปลี่ยน
9. เปิดไฟล์ layout หน้าหลัก
10. ก้อบ โค้ดด้านล่างไปใส่
```html
<Button
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="POPUP" 
android:onClick="popView" />
```
11. Recompile จบ

# แก้ดูหน้าเว็บไม่ได้
เพิ่ม <uses-permission android:name="android.permission.INTERNET"/>
ใส่ใน AndroidManifest.xml
