---
isChild: true
anchor:  windows_setup
---

## การเซ็ตอัปบนวินโดวส์ {#windows_setup_title}

คุณสามารถดาวน์โหลดไฟล์ไบนารีจาก [windows.php.net/download][php-downloads] และหลังจากแตกไฟล์ออกมาแล้ว  เราแนะนำให้ทำการตั้งค่า [PATH][windows-path] ให้ชี้มายังโฟลเดอร์ PHP ที่เพิ่งแตกออกมา (ที่ที่เก็บไฟล์ php.exe) ซึ่งจะช่วยให้คุณสามารถเรียกใช้งาน PHP ผ่าน command line ได้จากทุกที่

สำหรับผู้เริ่มเรียนรู้  หรือการพัฒนาเว็บบนเครื่องตัวเอง  คุณสามารถใช้เซิร์ฟเวอร์ built-in ที่มากับ PHP 5.4 เป็นต้นมา  หรือหากคุณต้องการตัวเลือกแบบ "all-in-one" ที่จะมาพร้อมกับเว็บเซอร์เวอร์และระบบฐานข้อมูลเช่น MySQL คุณสามารถติดตั้งซอฟต์แวร์เหล่านี้ได้เช่น [Web Platform Installer][wpi], [XAMPP][xampp], [EasyPHP][easyphp], [OpenServer][openserver] หรือ [WAMP][wamp] อย่างไรก็ตาม  การตั้งค่าในซอฟต์แวร์เหล่านี้มักจะต่างกันกับบนเซิร์ฟเวอร์ production จริง  ดังนั้นในการพัฒนาก็ควรคำนึกถึงความแตกต่างของเครื่องพัฒนาและเซิร์ฟเวอร์จริงที่มักเป็นระบบปฏิบัติการลินิกซ์ด้วย

ถ้าหากคุณดีพลอยแอปพลิเคชัน PHP ไปยังเซิร์ฟเวอร์ที่เป็นระบบปฏิบัติการวินโดส์ IIS7 จะเป็นตัวเลือกที่เสถียรและมีประสิทธิภาพที่สุด  คุณสามารถใช้ [phpmanager][phpmanager] ซึ่งเป็นปลั๊กอินแบบ GUI ของ IIS7 ในการช่วยตั้งค่าและจัดการ PHP

IIS7 นั้นมาพร้อมกับ FastCGI ในตัว  ที่คุณต้องทำนั้นมีเพียงแค่ตั้งค่าให้ PHP มาเป็น handler เท่านั้น  สำหรับความช่วยเหลือและข้อมูลอื่นๆ สามารถอ่านได้จาก[หมวด PHP บน iis.net][php-iis]

โดยปกติแล้วการรันแอปพลิเคชันบนสภาพแวดล้อมที่ต่างกันระหว่างเครื่องพัฒนาและเซิร์ฟเวอร์จริงมักจะทำให้เปิดบั๊กแปลกๆ อยู่เสมอ  ดังนั้นหากคุณพัฒนาบนระบบปฏิบัติการวินโดวส์และดีพลอยขึ้นเซิร์ฟเวอร์ที่ใช้ระบบปฏิบัติการลินิกซ์ (หรือระบบอื่นๆ ที่ไม่ใช่วินโดวส์) คุณอาจจะเลือกใช้ Virtual Machine ในการพัฒนาแทน

Chris Tankersley ได้เขียนบล็อกเกี่ยวกับเครื่องมือที่เขาใช้ในการพัฒนา PHP บนวินโดวส์เอาไว้ [PHP development using Windows][windows-tools].

[easyphp]: http://www.easyphp.org/
[phpmanager]: http://phpmanager.codeplex.com/
[openserver]: http://open-server.ru/
[wamp]: http://www.wampserver.com/en/
[php-downloads]: http://windows.php.net/download/
[php-iis]: http://php.iis.net/
[windows-path]: http://www.windows-commandline.com/set-path-command-line/
[windows-tools]: http://ctankersley.com/2016/11/13/developing-on-windows-2016/
[wpi]: https://www.microsoft.com/web/downloads/platform.aspx
[xampp]: http://www.apachefriends.org/en/xampp.html
