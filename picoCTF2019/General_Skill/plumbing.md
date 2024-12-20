# plumbing

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2019, General Skills, Medium
Author: ALEX FULTON/DANNY TUNITIS

Description:
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? 

Connect to jupiter.challenges.picoctf.org 4427

Hints:
1. Remember the flag format is picoCTF{XXXX}
2. What's a pipe? No not that kind of pipe... This kind
```
Challenge link: [https://play.picoctf.org/practice/challenge/48](https://play.picoctf.org/practice/challenge/48)

## Solution

Saya mencoba menghubungkan ke server dengan `nc`
```bash
┌──(kali㉿kali)-[/Downloads]
└─$ nc jupiter.challenges.picoctf.org 4427
Not a flag either
Again, I really don't think this is a flag
I don't think this is a flag either
This is defintely not a flag
Again, I really don't think this is a flag
Not a flag either
I don't think this is a flag either
Again, I really don't think this is a flag
Again, I really don't think this is a flag
This is defintely not a flag
This is defintely not a flag
This is defintely not a flag
This is defintely not a flag
Not a flag either
Again, I really don't think this is a flag
Not a flag either
<---more--->
```

Terlalu Banyak output. Mungkin bisa menggunakan `grep` untuk mendapatkan flag
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ nc jupiter.challenges.picoctf.org 4427 | grep picoCTF
picoCTF{digital_plumb3r_5ea1fbd7}
```

And there we have the flag.

For additional information, please see the references below.

## References

- [Pipes: A Brief Introduction](http://www.linfo.org/pipes.html)
- [grep(1) - Linux man page](https://linux.die.net/man/1/grep)
- [nc(1) - Linux man page](https://linux.die.net/man/1/nc)
