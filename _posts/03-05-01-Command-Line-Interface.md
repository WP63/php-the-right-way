---
title: การใช้งานผ่านคอมมานด์ไลน์
isChild: true
anchor:  command_line_interface
---

## การใช้งานผ่านคอมมานด์ไลน์ {#command_line_interface_title}

แม้ PHP จะถูกสร้างขึ้นมาเพื่อใช้เขียนเว็บแอปพลิเคชัน  แต่ PHP ยังสามารถใช้เขียนสคริปท์ที่ทำงานบน command-line interface (CLI) ได้ด้วย  ซึ่งโปรแกรม PHP ที่ทำงานผ่านคอมมานด์ไลน์นั้นสามารถใช้ในงาน automation ต่างๆ เช่นการทำเทสต์, การดีพลอย, และการจัดการแอปพลิเคชัน

โปรแกรม PHP ผ่าน CLI นั้นค่อนข้างอิสระ  เพราะคุณสามารถเขียนโค้ดของคุณให้ทำงานได้โดยตรงโดยไม่จำเป็นต้องทำส่วนติดต่อผู้ใช้ผ่านหน้าเว็บ  แต่ให้ระลึกไว้เสมอว่าอย่าเอาสคริปท์ PHP สำหรับ CLI ไปวางไว้บน public directory บนเซิร์ฟเวอร์ของคุณ!

ลองรันโค้ด PHP จากคอมมานด์ไลน์ของคุณ:

{% highlight console %}
> php -i
{% endhighlight %}

ออพชัน `-i` จะแสดงการตั้งค่าของ PHP เหมือในฟังก์ชัน [`phpinfo()`][phpinfo]

ออพชัน `-a` จะเป็นการเปิดใช้่ interactive shell ในลักษณะเดียวกันกับ IRB ของ Ruby หรือ interactive shell ของ Python และยังมี[ออพชันคอมมานด์ไลน์][cli-options]อื่นๆ อีกมากมาย

ลองเขียนแอปพลิเคชัน "Hello, $name" ง่ายๆ บน CLI โดยการสร้างไฟล์ `hello.php` ด้วยโค้ดนี้

{% highlight php %}
<?php
if ($argc !== 2) {
    echo "Usage: php hello.php <name>.\n";
    exit(1);
}
$name = $argv[1];
echo "Hello, $name\n";
{% endhighlight %}

PHP sets up two special variables based on the arguments your script is run with. [`$argc`][argc] is an integer
variable containing the argument *count* and [`$argv`][argv] is an array variable containing each argument's *value*.
The first argument is always the name of your PHP script file, in this case `hello.php`.

The `exit()` expression is used with a non-zero number to let the shell know that the command failed. Commonly used
exit codes can be found [here][exit-codes].

To run our script, above, from the command line:

{% highlight console %}
> php hello.php
Usage: php hello.php <name>
> php hello.php world
Hello, world
{% endhighlight %}


 * [อ่านเพิ่มเติมเกี่ยวกับการใช้งาน PHP ผ่านคอมมานด์ไลน์][php-cli]

[phpinfo]: https://secure.php.net/function.phpinfo
[cli-options]: https://secure.php.net/features.commandline.options
[argc]: https://secure.php.net/reserved.variables.argc
[argv]: https://secure.php.net/reserved.variables.argv
[exit-codes]: https://www.gsp.com/cgi-bin/man.cgi?section=3&amp;topic=sysexits
[php-cli]: https://secure.php.net/features.commandline.options
