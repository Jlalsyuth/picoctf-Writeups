# Warmed Up

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2019, General Skills, Easy
Author: SANJAY C/DANNY TUNITIS

Description:
What is 0x3D (base 16) in decimal (base 10)?

Hints:
1. Submit your answer in our flag format. For example, if your answer was '22', 
   you would submit 'picoCTF{22}' as the flag.
```
Challenge link: [https://play.picoctf.org/practice/challenge/58](https://play.picoctf.org/practice/challenge/58)

## Solution

### Convert in Python

We can use an interactive Python session to do the work for us with the [str function](https://docs.python.org/3/library/functions.html#func-str) and the fact that Python understands [hexadecimal numbers](https://en.wikipedia.org/wiki/Hexadecimal)
```bash
┌──(kali㉿kali)-[/Downloads/Warmed_Up]
└─$ python
Python 3.11.9 (main, Apr 10 2024, 13:16:36) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print('picoCTF{' + str(0x3d) + '}')
picoCTF{61}
>>> exit()
```


## References

- [Wikipedia - Hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal)
