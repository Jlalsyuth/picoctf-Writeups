# Bases

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2019, General Skills, Easy
Author: SANJAY C/DANNY T
 
Description:
What does this bDNhcm5fdGgzX3IwcDM1 mean? 

I think it has something to do with bases.

Hints:
1. Submit your answer in our flag format. For example, if your answer was 'hello', 
   you would submit 'picoCTF{hello}' as the flag.
```
Challenge link: [https://play.picoctf.org/practice/challenge/67](https://play.picoctf.org/practice/challenge/67)

## Solution

Ini adalah [Base64 encoding](https://en.wikipedia.org/wiki/Base64) dan ada cara lain untuk melakukan decode.

### Dengan Skrip Python

```python
#!/usr/bin/python

from base64 import b64decode

enc = 'bDNhcm5fdGgzX3IwcDM1'

decoded = b64decode(enc).decode()
print(f"picoCTF{{{decoded}}}")
```

Then we make sure the script is executable and run it to get the flag
```bash
┌──(kali㉿kali)-[~/Downloads/Bases]
└─$ chmod +x decode.py     

┌──(kali㉿kali)-[~/Downloads/Bases]
└─$ ./decode.py       
picoCTF{l3arn_th3_r0p35}
```

## References

- [Wikipedia - Base64](https://en.wikipedia.org/wiki/Base64)
