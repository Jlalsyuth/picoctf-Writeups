# First Grep

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2019, General Skills, Easy
Author: ALEX FULTON/DANNY TUNITIS

Description:
Can you find the flag in file? 

This would be really tedious to look through manually, something tells me there is a better way.
 
Hints:
1. grep tutorial
```
Challenge link: [https://play.picoctf.org/practice/challenge/85](https://play.picoctf.org/practice/challenge/85)

## Solution

Ini pada dasarnya adalah tutorial yang sangat mudah untuk fungsi `grep`
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cat file | grep picoCTF
picoCTF{grep_is_good_to_find_things_f77e0797}}
```

## References
- [Grep and Regular Expressions!](https://ryanstutorials.net/linuxtutorial/grep.php)
