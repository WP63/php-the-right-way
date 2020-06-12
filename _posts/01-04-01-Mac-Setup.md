---
isChild: true
anchor:  mac_setup
---

## การเซ็ตอัปบนแมค {#mac_setup_title}

macOS นั้นมีแพ็คเกจ PHP มาให้ในตัวอยู่แล้ว  แต่มักจะเป็นเวอร์ชันเก่ากว่าปัจจุบันอยู่เล็กน้อย  หากต้องการติดตั้ง PHP เวอร์ชันล่าสุดบนแมค  คุณมีทางเลือกดังต่อไปนี้

### ติดตั้ง PHP ผ่าน Homebrew

[Homebrew] เป็นตัวจัดการแพ็คเกจสำหรับ macOS ซึ่งคุณสามารถติดตั้ง PHP และส่วนขยายต่างๆ เพิ่มเติมผ่าน Homebrew ได้โดยง่ายผ่านคำสั่งต่อไปนี้

```
brew install php@7.4
```

Homebrew รองรับการติดตั้ง PHP และส่วนขยายสำหรับเวอร์ชัน 5.6, 7.0, 7.1, 7.2, 7.3, และ 7.4

คุณสามารถสลับเวอร์ชันของ PHP ที่ติดตั้งจาก Homebrew ไปมาได้ด้วยการแก้ไขตัวแปร `PATH` ของ shell ที่ใช้  หรืออีกทางเลือกหนึ่งคือติดตั้งแพ็คเกจ [brew-php-switcher][brew-php-switcher] สำหรับใช้สลับเวอร์ชัน PHP โดยอัตโนมัติ

### ติดตั้ง PHP ผ่าน Macports

[MacPorts] นั้นเป็นโครงการโอเพนซอร์สที่ออกแบบมาเพื่อสร้างระบบคอมไพล์, ติดตั้ง, และอัปเกรดซอฟต์แวร์ต่างๆ ได้โดยง่าย  ไม่ว่าจะเป็นซอฟต์แวร์บน command-line, ซอฟต์แวร์ X11, หรือซอฟต์แวร์ Aqua บนระบบปฏิบัติการ macOS

MacPorts รองรับไบนารี่ที่คอมไพล์มาแล้ว  ดังนั้นคุณไม่จำเป็นที่จำต้องคอมไพล์ dependencies ต่างๆ จากซอร์สโค้ดเองทั้งหมด  ซึ่งช่วยให้คุณไม่ต้องปวดหัวหากคุณไม่มีแพ็คเกจเหล่านั้นติดตั้งเอาไว้บนเครื่องของคุณ

ในตอนนี้คุณสามารถติดตั้งแพ็คเกจ `php54`, `php55`, `php56`, `php70`, `php71`, `php72`, `php73` หรือ `php74` ผ่านคำสั่ง `port install` เพื่อติดตั้งผ่าน MacPorts ตัวอย่างเช่น:

    sudo port install php56
    sudo port install php74

และคุณสามารถใช้คำสั่ง `select` เพื่อสลับเวอร์ชันของ PHP ได้:

    sudo port select --set php php74

### ติดตั้ง PHP ผ่าน phpbrew

[phpbrew] เป็นเครื่องมือสำหรับติดตั้งและจัดการ PHP หลายเวอร์ชันพร้อมกัน  เครื่องมือนี้จะมีประโยชน์เมื่อคุณมีโปรเจ็กท์หลายโปรเจ็กท์ที่ใช้ PHP ต่างรุ่นกัน  และคุณไม่ต้องการใช้ virtual machines

### ติดตั้ง PHP ผ่านตัวติดตั้ง Liip

ตัวเลือกที่เป็นที่นิยมอีกตัวหรือคือ [php-osx.liip.ch] ที่เป็นตัวช่วยติดตั้ง PHP ตั้งแต่เวอร์ชัน 5.3 ถึง 7.3 ได้ด้วยคำสั่งเพียงบรรทัดเดียว  การติดตั้งด้วยวิธีนี้จะไม่ติดตั้ง PHP ทับแพ็คเกจที่มากับ macOS แต่จะติดตั้งทุกอย่างแยกกันต่างหาก (/usr/local/php5)

### คอมไพล์จากซอร์สโค้ด

อีกทางเลือกหนึ่งที่คุณสามารถติดตั้ง PHP ได้นั่นคือ[คอมไพล์จากซอร์สโค้ดด้วยตัวคุณเอง][mac-compile]  วิธีนี้คุณจำเป็นจะต้องติดตั้ง [Xcode][xcode-gcc-substitution] หรือเครื่องมือ ["Command Line Tools for XCode"] ของแอปเปิล  ที่คุณสามารถดาวน์โหลดได้จาก Mac Developer Center

### ตัวติดตั้งแบบ All-in-One

ตัวเลือกด้านบนจะเป็นแค่การติดตั้ง PHP เท่านั้นโดยที่ไม่มีซอฟต์แวร์อื่นๆ เช่น [Apache][apache], [Nginx][nginx], หรือ SQL Server มาให้  ตัวติดตั้งแบบ All-in-one อย่างเช่น [MAMP][mamp-downloads] และ [XAMPP][xampp] จะติดตั้งซอฟต์แวร์อื่นๆ ที่ใช้ร่วมกันเช่น Apache และ MySQL (หรือ MariaDB) มาให้พร้อมกันด้วย  แต่การปรับแต่งต่างๆ ก็จะค่อนข้างจำกัดมากกว่า

[Homebrew]: https://brew.sh/
[Homebrew PHP]: https://github.com/Homebrew/homebrew-php#installation
[MacPorts]: https://www.macports.org/install.php
[phpbrew]: https://github.com/phpbrew/phpbrew
[php-osx.liip.ch]: https://php-osx.liip.ch/
[mac-compile]: https://secure.php.net/install.macosx.compile
[xcode-gcc-substitution]: https://github.com/kennethreitz/osx-gcc-installer
["Command Line Tools for XCode"]: https://developer.apple.com/downloads
[apache]: https://httpd.apache.org/
[nginx]: https://www.nginx.com/
[mamp-downloads]: https://www.mamp.info/en/downloads/
[xampp]: https://www.apachefriends.org/index.html
[brew-php-switcher]: https://github.com/philcook/brew-php-switcher
