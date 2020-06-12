---
title:  มาตรฐานการเขียนโค้ด
anchor: code_style_guide
---

# มาตรฐานการเขียนโค้ด {#code_style_guide_title}

PHP มีชุมชนผู้ใช้ขาดใหญ่และหลากหลาย  เต็มไปด้วยไลบรารี่, เฟรมเวิร์ก, และคอมโพเนนท์ต่างๆ จำนวนมาก  ซึ่งเป็นเรื่องปกติที่นักพัฒนาภาษา PHP จะเลือกใช้โค้ดต่างๆ จากตรงนี้และประกอบมันขึ้นมาเป็นโปรเจ็กท์สักโปรเจ็กท์หนึ่ง  นั่นทำให้รูปแบบการเขียนโค้ดของนักพัฬนาแต่ละคนนั้นควรจะใกล้เคียงกันเป็นมาตรฐานให้มากที่สุด  เพื่อให้นักพัฒนาคนอื่นสามารถอ่านและนำโค้ดไปใช้ในโปรเจ็กท์ของพวกเขาได้ไม่ยากเย็นนัก

กลุ่ม [Framework Interop Group][fig] ได้เสนอและแนะนำเกณฑ์กลางเกี่ยวกับ PHP แม้ว่าจะไม่ใช่เรื่องของการเขียนโค้ดทั้งหมด (บางเรื่องเกี่ยวกับโครงสร้างของคลาสบางประเภท และอื่นๆ) แต่หัวข้ออย่าง [PSR-1][psr1], [PSR-12][psr12], และ [PSR-4][psr4] นั้นเกี่ยวกับการเขียนโค้ดโดยตรง  คำแนะนำเหล่านี้จะเป็นเกณฑ์การเขียนโค้ด  ซึ่งโครงการจำนวนมากเช่น Drupal, Zend, Symfony, Laravel, CakePHP, phpBB, AWS SDK, FuelPHP, Lithium, และอื่นๆ ได้นำไปปรับใช้แล้ว  ทั้งนี้คุณอาจจะนำไปปรับใช้กับโปรเจ็กท์ของคุณ  หรืออาจจะใช้รูปแบบของคุณเองก็ได้

แต่จริงๆ แล้วคุณควรจะเขียนโค้ดโดยอ้างอิงกับมาตรฐานที่เป็นที่รับรู้กัน  ซึ่งอาจจะเป็นมาตรฐาน PSR ต่างๆ, หรืออาจจะเป็นมาตรฐานโค้ดที่แนะนำโดย PEAR หรือ Zend ก็ได้  ซึ่งการเขียนโค้ดโดยอิงกับมาตรฐานเหล่านีั้จะช่วยให้นักพัฒนาคนอื่น (โดยเฉพาะคนที่รับงานของคุณไปทำต่อ) สามารถอ่านและเข้าใจโค้ดของคุณได้ง่ายขึ้น  รวมการันตีได้ว่าแอปพลิเคชันอื่นๆ ที่เรียกใช้โค้ดของคุณ  จะรูปแบบโค้ดที่เข้ากันได้กับไลบรารี่อื่นๆ ที่ใช้งาน

* [อ่านเกี่ยวกับ PSR-1][psr1]
* [อ่านเกี่ยวกับ PSR-12][psr12]
* [อ่านเกี่ยวกับ PSR-4][psr4]
* [อ่านเกี่ยวกับ PEAR Coding Standards][pear-cs]
* [อ่านเกี่ยวกับ Symfony Coding Standards][symfony-cs]

คุณสามารถใช้ [PHP_CodeSniffer][phpcs] เพื่อตรวจสอบดูว่าโค้ดใดๆ ของคุณนั้นเขียนได้ถูกต้องตามหลักมาตรฐานเหล่านี้หรือไม่  Text Editor หลายๆ ตัวอย่าง [Sublime Text][st-cs] และ [Visual Studio Code][vsc-cs] นั้นมีส่วนเสริมที่ช่วยตรวจสอบโค้ดแบบเรียลไทม์

นอกจากนี้คุณยังสามารถใช้เครื่องมือเหล่านี้ในการตรวจสอบและแก้ไขโค้ดบางอย่างได้อัตโนมัติ:

- ตัวเลือกแรกคือ [PHP Coding Standards Fixer][phpcsfixer] ซึ่งเป็นโครงการที่ได้รับการทดสอบมาแล้วอย่างดี
- และอีกตัวเลือกคือ [PHP Code Beautifier and Fixer][phpcbf] ซึ่งเป็นเครื่องมือที่มาพร้อมกับ PHP_CodeSniffer ที่สามารถใช้ปรับโค้ดของคุณให้ถูกต้องได้

หรือคุณอาจจะรันคำสั่งนี้เองใน command line ก็ได้:

    phpcs -sw --standard=PSR1 file.php

คำสั่งนี้จะแสดงข้อผิดพลาดและคำแนะนำในการแก้ไข  และผู้ใช้ที่ git อาจจะพ่วงคีำสั่งนี้เข้าไปใน git hook เพื่อใช้ตรวจสอบโค้ดก่อนการคอมมิตได้ด้วยเช่นกัน

เมื่อคุณติดตั้ง PHP_CodeSniffer แล้ว  คุณยังสามารถใช้คำสั่งนี้เพื่อให้ [PHP Code Beautifier and Fixer][phpcbf] ทำการแก้ไขข้อผิดพลาดให้โดยอัตโนมัติ

    phpcbf -w --standard=PSR1 file.php

อีกทางเลือกนั่นคือใช้ [PHP Coding Standards Fixer][phpcsfixer] ในการแก้ไข  โดยเครื่องมือตัวนี้จะแสดงข้อผิดพลาดก่อนการแก้ไขให้ด้วย

    php-cs-fixer fix -v --rules=@PSR1 file.php

เราแนะนำให้ใช้ภาษาอังกฤษเป็นหลักในการตั้งชื่อซิมโบลและไฟล์ต่างๆ  แต่คุณสามารถเขียนคอมเมนต์ด้วยภาษาใดก็ได้  หากคุณมั่นใจว่าคนที่จะนำโค้ดของคุณไปใช้สามารถอ่านมันออก

และสุดท้าย  เราแนะนำให้ลองดูตัวอย่างใน repo นี้ว่าโค้ดที่สะอาดนั้นเป็นอย่างไร [Clean Code PHP][cleancode].

[fig]: https://www.php-fig.org/
[psr1]: https://www.php-fig.org/psr/psr-1/
[psr12]: https://www.php-fig.org/psr/psr-12/
[psr4]: https://www.php-fig.org/psr/psr-4/
[pear-cs]: https://pear.php.net/manual/en/standards.php
[symfony-cs]: https://symfony.com/doc/current/contributing/code/standards.html
[phpcs]: https://pear.php.net/package/PHP_CodeSniffer/
[phpcbf]: https://github.com/squizlabs/PHP_CodeSniffer/wiki/Fixing-Errors-Automatically
[st-cs]: https://github.com/benmatselby/sublime-phpcs
[vsc-cs]: https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs
[phpcsfixer]: https://cs.sensiolabs.org/
[cleancode]: https://github.com/jupeter/clean-code-php
