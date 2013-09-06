otfile
======

Serve a single file, once, via HTTP over the local network.

Requirements
====
* Perl 5.10.1


Optional Dependencies
====

otfile will make use of the following modules, if available:

* Term::Progressbar
* Mac::Pasteboard - For auto-copying generated URL to the clipboard
* File::MMagic - For detecting and setting correct MIME-type, otherwise ```application/data``` is used.
* UUID::Tiny - For generating a UUID for the path, otherwise a random string is used.
* URI::Escape - If unsafe characters are in filename, they will be escaped by URI::Escape if it is present, otherwise, otfile will die with an error.

Usage
====

```
~docs $ otfile Mailbox.numbers
Serving 'Mailbox.numbers' as 'Mailbox.numbers', size 302497, type application/x-zip
http://192.168.199.188:1234/b5ad48cc-1736-11e3-a580-8f068ecdf712/Mailbox.numbers copied to clipboard.
```

Send the URL to your coworker, they download it and you see:

```
I: Connect from 192.168.199.188
Mailbox.numbers: 100% [======]D 0h00m00s
Done.
~docs $
```

Credit
====
This script based on one shamelessly stolen from some guys blog post years ago.  I don't remember where I found the idea but it was a great one.  If you see this please tell me who you are so I can thank you!