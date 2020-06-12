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

PHP supports first-class functions, meaning that a function can be assigned to a variable. Both user-defined and
built-in functions can be referenced by a variable and invoked dynamically. Functions can be passed as arguments to
other functions (a feature called _Higher-order Functions_) and functions can return other functions.

Recursion, a feature that allows a function to call itself, is supported by the language, but most PHP code
is focused on iteration.

New anonymous functions (with support for closures) are present since PHP 5.3 (2009).

PHP 5.4 added the ability to bind closures to an object's scope and also improved support for callables such that they
can be used interchangeably with anonymous functions in almost all cases.

* Continue reading on [Functional Programming in PHP](pages/Functional-Programming.html)
* [อ่านเกี่ยวกับ Anonymous Functions][anonymous-functions]
* [อ่านเกี่ยวกับ the Closure class][closure-class]
* [รายละเอียดเพิ่มเติมใน Closures RFC][closures-rfc]
* [อ่านเกี่ยวกับ Callables][callables]
* [อ่านเกี่ยวกับ dynamically invoking functions with `call_user_func_array()`][call-user-func-array]

### เมทาโปรแกรมมิ่ง

PHP supports various forms of meta-programming through mechanisms like the Reflection API and Magic Methods. There are
many Magic Methods available like `__get()`, `__set()`, `__clone()`, `__toString()`, `__invoke()`, etc. that allow
developers to hook into class behavior. Ruby developers often say that PHP is lacking `method_missing`, but it is
available as `__call()` and `__callStatic()`.

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

