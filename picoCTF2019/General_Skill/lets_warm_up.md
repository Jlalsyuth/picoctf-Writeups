# Lets Warm Up

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2019, General Skills, Easy
Author: SANJAY C/DANNY TUNITIS

Description:
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
 
Hints:
1. Submit your answer in our flag format. For example, if your answer was 'hello', 
   you would submit 'picoCTF{hello}' as the flag.
```
Challenge link: [https://play.picoctf.org/practice/challenge/22](https://play.picoctf.org/practice/challenge/22)

## Solution

Kita dapat mencari jawabannya secara manual dengan [ASCII table](https://www.ascii-code.com/) atau menggunakan fungsi dari python [chr function](https://docs.python.org/3/library/functions.html#chr)
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ python                
Python 3.11.9 (main, Apr 10 2024, 13:20:36) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print('picoCTF{' + chr(0x70) + '}') 
picoCTF{p}
>>> exit()
```



## References

- [Wikipedia - ASCII](https://en.wikipedia.org/wiki/ASCII)
- [ASCII Table](https://www.ascii-code.com/)
