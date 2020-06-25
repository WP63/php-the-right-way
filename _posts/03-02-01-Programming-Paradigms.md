---
title:   กระบวนการทางโปรแกรม
isChild: true
anchor:  programming_paradigms
---

## กระบวนการทางโปรแกรม {#programming_paradigms_title}

PHP เป็นภาษาที่ยืดหยุ่น  สามารถใช้ในการเขียนโค้ดได้ในหลายรูปแบบ  และมีการพัฒนาปรับปรุงอย่างต่อเนื่องในทุกๆ ปี  สิ่งหนึ่งที่เห็นได้ชัดนั่นคือการรองรับการเขียนโปรแกรมในเชิงวัตถุอย่างเต็มรูปแบบเข้ามาใน PHP 5.0 (2004), การรองรับ anonymous function และ namespace ใน PHP 5.3, และการรองรับ trait ใน PHP 5.4 (2012)

### การเขียนโปรแกรมเชิงวัตถุ

PHP has a very complete set of object-oriented programming features including support for classes, abstract classes,
interfaces, inheritance, constructors, cloning, exceptions, and more.

* [อ่านเกี่ยวกับ Object-oriented PHP][oop]
* [อ่านเกี่ยวกับ Traits][traits]

### การเขียนโปรแกรมเชิงฟังก์ชัน

PHP รองรับ first-class functions นั่นคือคุณสามารถกำหนดค่าของตัวแปรต่างๆ เป็นฟังก์ชันได้  ทั้งฟังก์ชันที่มากับ PHP และฟังก์ชันที่ผู้ใช้เขียนเองสามารถถูกเรียกได้ผ่านตัวแปรและจะถูก invoke ขึ้นมาแบบ dynamic และเรายังสามารถส่งฟังก์ชันเข้าไปเป็นอาร์กิวเมนต์ของฟังก์ชันอื่นได้ด้วย (หรือที่เรียกว่า _Higher-order functions_) รวมถึงฟังก์ชันต่างๆ สามารถคืนค่ากลับออกมาเป็นฟังก์ชันได้ด้วยเช่นกัน

นอกจากนี้ PHP ยังรองรับฟังก์ชันแบบ recursion หรือฟังก์ชันที่เรียกใช้ตัวมันเองด้วย  แต่โค้ด PHP ส่วนมากจะใช้แบบ iteration เสียมากกว่า

ใน PHP 5.3 (ออกเมื่อปี 2009) PHP ยังรองรับ anomymouse ฟังก์ชัน รวมถึงคลาส closure

ใน PHP 5.4 ได้มีการเพิ่มความสามารถในการ bind closures เข้ากับสโคปของออพเจ็กท์  และปรับปรุง callables ให้สามารถใช้แทนกันกับ anonymouse functions ในสถานการณ์ส่วนใหญ่ได้ด้วย

* อ่านเพิ่มเติมเกี่ยวกับ [Functional Programming in PHP](pages/Functional-Programming.html)
* [อ่านเกี่ยวกับ Anonymous Functions][anonymous-functions]
* [อ่านเกี่ยวกับ the Closure class][closure-class]
* [รายละเอียดเพิ่มเติมใน Closures RFC][closures-rfc]
* [อ่านเกี่ยวกับ Callables][callables]
* [อ่านเกี่ยวกับ dynamically invoking functions with `call_user_func_array()`][call-user-func-array]

### เมทาโปรแกรมมิ่ง

PHP รองรับ meta-programming ผ่านฟีเจอร์อย่าง Reflection API และ Magic Methods และ PHP นั้นมี Magic Methods อยู่หลายตัวเช่น `__get()`, `__set()`, `__clone()`, `__toString()`, `__invoke()`, และอื่นๆ  ซึ่ง Magic Methods เหล่านี้เปิดให้นักพัฒนาสามารถฮุคเข้าไปในการทำงานต่างๆ ของคลาสได้

นักพัฒนาภาษา Ruby มักบอกว่าภาษา PHP นั้นขาดฟีเจอร์อย่าง `method_missing` ที่จะทำงานเมื่อมีการเรียกใช้เมท็อดที่ไม่มีอยู่หรือเข้าถึงไม่ได้  แต่จริงๆ PHP รองรับฟีเจอร์นี้ผ่าน Magic Methods `__call()` และ `__callStatic()`

* [อ่านเกี่ยวกับ Magic Methods][magic-methods]
* [อ่านเกี่ยวกับ Reflection][reflection]
* [อ่านเกี่ยวกับ Overloading][overloading]


[oop]: https://secure.php.net/language.oop5
[traits]: https://secure.php.net/language.oop5.traits
[anonymous-functions]: https://secure.php.net/functions.anonymous
[closure-class]: https://secure.php.net/class.closure
[closures-rfc]: https://wiki.php.net/rfc/closures
[callables]: https://secure.php.net/language.types.callable
[call-user-func-array]: https://secure.php.net/function.call-user-func-array
[magic-methods]: https://secure.php.net/language.oop5.magic
[reflection]: https://secure.php.net/intro.reflection
[overloading]: https://secure.php.net/language.oop5.overloading

