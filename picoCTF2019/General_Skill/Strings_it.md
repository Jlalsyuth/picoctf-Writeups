# strings it

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2019, General Skills, Easy
Author: SANJAY C/DANNY TUNITIS

Description:
Can you find the flag in file without running it?

Hints:
1. strings
```
Challenge link: [https://play.picoctf.org/practice/challenge/37](https://play.picoctf.org/practice/challenge/37)

## Solution

ini menggunakan basic `strings` dan `grep`
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ strings strings | grep pico       
picoCTF{5tRIng5_1T_d66c7bb7}
```


## References

- [grep - Linux manual page](https://man7.org/linux/man-pages/man1/grep.1.html)
- [strings - Linux manual page](https://man7.org/linux/man-pages/man1/strings.1.html)
