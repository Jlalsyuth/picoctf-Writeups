# mus1c

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2019, General Skills, Medium
Author: DANNY

Description:
I wrote you a song. Put it in the picoCTF{} flag format.

Hints:
1. Do you think you can master rockstar?
```
Challenge link: [https://play.picoctf.org/practice/challenge/15](https://play.picoctf.org/practice/challenge/15)

## Solution

Dibawah ini adalah isi dari konten yang diberikan
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cat lyrics.txt              
Pico's a CTFFFFFFF
my mind is waitin
It's waitin

Put my mind of Pico into This
my flag is not found
put This into my flag
put my flag into Pico


shout Pico
shout Pico
shout Pico

My song's something
put Pico into This

Knock This down, down, down
put This into CTF

shout CTF
my lyric is nothing
Put This without my song into my lyric
Knock my lyric down, down, down

shout my lyric

Put my lyric into This
Put my song with This into my lyric
Knock my lyric down

shout my lyric

Build my lyric up, up ,up

shout my lyric
shout Pico
shout It

Pico CTF is fun
security is important
Fun is fun
Put security with fun into Pico CTF
Build Fun up
shout fun times Pico CTF
put fun times Pico CTF into my song

build it up

shout it
shout it

build it up, up
shout it
shout Pico
```

Ini seperti bahasa pemrograman [Rockstar](https://esolangs.org/wiki/Rockstar) saya langsung mencoba [online emulator](https://codewithrockstar.com/online) karena ini seperti soal sebelumnya 1_wanna_b3_a_r0ck5tas.

Copy dan paste kode programnya dibagian atas emulator dan tekan `Rock!`.  
Jadi saya mendapatkan output seperti dibawah
```
114
114
114
111
99
107
110
114
110
48
49
49
51
114
Program completed in 168 ms
```

Karena dari angka tersebut sudah kelihatan merupakan ascii maka langsung saja saya menggunakan konverter online 

![image](https://github.com/user-attachments/assets/9152d8df-b37f-4dd6-a3fb-e12caf25707a)

Jadi Flagnya adalah: picoCTF{rrrocknrn0113r}

## References

- [Rockstar](https://esolangs.org/wiki/Rockstar)
- [Rockstar Online Emulator](https://codewithrockstar.com/online)
