# Tab, Tab, Attack

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2021, General Skills, Easy
Author: SYREAL

Description:
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with 
long rambling directory structures and filenames: Addadshashanammu.zip
 
Hints:
1. After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...
```
Challenge link: [https://play.picoctf.org/practice/challenge/176](https://play.picoctf.org/practice/challenge/176)

## Solution

Inti dari tantangan ini adalah melatih cara menggunakan [tab completion](https://en.wikipedia.org/wiki/Command-line_completion).

Pertama, perlu dilakukan unpack untuk file tersebut dengan `unzip`
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
```

Langsung saja menuju directorynya dengan `cd`
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku 

┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls
fang-of-haynekhtnamet
```

Saya cek ini merupakan file apa dengan `file`
```bash
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=fcea24fb5379795a123bb860267d815e889a6d23, not stripped
```

Ternyata ini 64-bit ELF binary.

Langsung saya jalankan
```bash
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ./fang-of-haynekhtnamet  
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
```

Dan itu adalah Flagnya

## References

- [file - Linux manual page](https://man7.org/linux/man-pages/man1/file.1.html)
- [unzip - Linux manual page](https://linux.die.net/man/1/unzip)
- [Wikipedia - Command-line completion](https://en.wikipedia.org/wiki/Command-line_completion)
