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
* Clipboard - For auto-copying generated URL to the clipboard
* File::MMagic - For detecting and setting correct MIME-type, otherwise ```application/data``` is used.
* UUID::Tiny - For generating a UUID for the path, otherwise a random string is used.
* URI::Escape - If unsafe characters are in filename, they will be escaped by URI::Escape if it is present, otherwise, otfile will die with an error.

Installation
====
```
$ curl -O https://raw.github.com/mikegrb/One-Time-File/master/script/otfile
$ # or
$ wget https://raw.github.com/mikegrb/One-Time-File/master/script/otfile
$ # then
$ chmod +x otfile
```

For best results, put somewhere in your path.  This script is also packaged on
the CPAN as ```App::otfile``` so you can install from there with your favorite
CPAN client.

```
$ cpanm App::otfile
```

Usage Example
====

```
~docs $ otfile Mailbox.numbers
Serving 'Mailbox.numbers' as 'Mailbox.numbers', size 302497, type application/x-zip
http://192.168.199.188:1234/b5ad48cc-1736-11e3-a580-8f068ecdf712/Mailbox.numbers copied to clipboard.
```

Send the URL to your coworker, they download it and you see:

```
I: Connect from 192.168.199.188
Mailbox.numbers: 100% [===============]D 0h00m00s
Done.
~docs $
```

Credit
====
This script based on one shamelessly stolen from some guys blog post years ago.  I don't remember where I found the idea but it was a great one.  If you see this please tell me who you are so I can thank you!

Usage Documentation
===

$ otfile \[-a -p 1234\] file_to_serve

# OPTIONS

- __\--auto__ or __\-a__

    Auto port selection.  increments specified port until successful.

- __\--port=N__ or __\-p N__

    Use specified port, defaults to 1234.

- __\--multiple__ or __\-m__

    Don't exit after serving the file the first time. To serve a file to multiple
    people. Requires, CTL+C to exit.

- __\--self__ or __\-s__

    Serve a copy of the otfile script.

- __\--help__ or __\-h__

    this help information
