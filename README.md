# DialogWebView-Smali
ป้อบอัพเว็บเมื่อจิ้มปุ่ม **ไว้ใช้แนวพวกแจ้งเตือน**  

![alt text](https://raw.githubusercontent.com/kaozaza2/DialogWebView-Smali/master/Screenshots/01.gif)

**Update to V2.0**  #ลบอันเก่าออกแล้วใส่อันใหม่

# ดาวน์โหลด
<a href="https://github.com/kaozaza2/DialogWebView-Smali/archive/master.zip">Here!!!</a>

# สิ่งที่ต้องใช้
1. ApkTool 2.0
2. คอมหรือโทรศัพท์
3. เวลาว่าง "มากๆ"

# How to
1. Decompile App.apk
2. คัดลอกโฟลเดอร์ com ไปใส่ในโฟลเดอร์ smali
3. เปิด AndroidManifest.xml แล้วหา ``` <category android:name="android.intent.category.LAUNCHER" /> ```
4. หา <activity android:name=" ที่อยู่ข้างบน ``` <category android:name="android.intent.category.LAUNCHER" /> ```
5. เปิดไฟล์ ที่ชื่อเดียวกับ <activity android:name="ตรงนี้" ......... > 
6. ค้นหา #virtual methods แล้วก้อบโค้ดด้านล่างไปใส่ข้างล่าง  #virtual methods
```smali
.method public popView(Landroid/view/View;)V
    .locals 0
    .param p1, "v"    # Landroid/view/View;

    .prologue
    invoke-static {p1}, Lcom/paper/PopupWebView/PopView;->PopView(Landroid/view/View;)V

    return-void
.end method
```
7. เปิดไฟล์ com/paper/PopupWebView/PopView.smali
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
เพิ่มโค้ดข้างล่างใส่ใน AndroidManifest.xml
```html
<uses-permission android:name="android.permission.INTERNET"/>
```
