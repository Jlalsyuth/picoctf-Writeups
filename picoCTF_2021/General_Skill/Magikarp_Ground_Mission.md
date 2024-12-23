# Magikarp Ground Mission

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2021, General Skills, Easy
Author: SYREAL

Description:
Do you know how to move between directories and read files in the shell? 

Start the container, `ssh` to it, and then `ls` once connected to begin. 

Login via `ssh` as `ctf-player` with the password, `abcba9f7`
 
Hints:
1. Finding a cheatsheet for bash would be really helpful!
```
Challenge link: [https://play.picoctf.org/practice/challenge/189](https://play.picoctf.org/practice/challenge/189)

## Solution

Jika dilihat dari hints-nya Tantangan ini merupakan menavigasi sistem file di bash

### Connect to the server

langsung connect ke server-nya dengan SSH
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ ssh ctf-player@venus.picoctf.net -p 59445        
The authenticity of host '[venus.picoctf.net]:59445 ([3.131.124.143]:59445)' can't be established.
ED25519 key fingerprint is SHA256:P1f6h95BrSVnJbm2AKhphfHHGEyAeThib/rN/AwKs24.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[venus.picoctf.net]:59445' (ED25519) to the list of known hosts.
ctf-player@venus.picoctf.net's password: 
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.
```

Cek untuk isi filenya
```bash
ctf-player@pico-chall$ ls -la
total 16
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar 16  2021 .
drwxr-xr-x 1 ctf-player ctf-player 4096 Aug 13 16:24 ..
-rw-r--r-- 1 ctf-player ctf-player   14 Mar 16  2021 1of3.flag.txt
-rw-r--r-- 1 ctf-player ctf-player   56 Mar 16  2021 instructions-to-2of3.txt
```

Ah, the first part of the flag.

### Getting the first part of the flag

Ini merupakan bagian dari flagnya jadi bisa disimpan dulu
```bash
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_
```

Lalu kita lanjutkan dengan mengikuti instruksinya
```bash
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls -la
total 92
drwxr-xr-x   1 root root 4096 Dec 22 13:24 .
drwxr-xr-x   1 root root 4096 Dec 22 13:24 ..
-rwxr-xr-x   1 root root    0 Dec 22 13:24 .dockerenv
-rw-r--r--   1 root root   17 Mar 16  2021 2of3.flag.txt
drwxr-xr-x   1 root root 4096 Mar 16  2021 bin
drwxr-xr-x   2 root root 4096 Apr 24  2018 boot
drwxr-xr-x   5 root root  340 Dec 22 13:24 dev
drwxr-xr-x   1 root root 4096 Dec 22 13:24 etc
drwxr-xr-x   1 root root 4096 Mar 16  2021 home
-rw-r--r--   1 root root   51 Mar 16  2021 instructions-to-3of3.txt
drwxr-xr-x   1 root root 4096 Mar 16  2021 lib
drwxr-xr-x   2 root root 4096 Feb 22  2021 lib64
drwxr-xr-x   2 root root 4096 Feb 22  2021 media
drwxr-xr-x   2 root root 4096 Feb 22  2021 mnt
drwxr-xr-x   1 root root 4096 Mar 16  2021 opt
dr-xr-xr-x 187 root root    0 Dec 22 13:24 proc
drwx------   2 root root 4096 Feb 22  2021 root
drwxr-xr-x   1 root root 4096 Dec 22 13:25 run
drwxr-xr-x   1 root root 4096 Mar 16  2021 sbin
drwxr-xr-x   2 root root 4096 Feb 22  2021 srv
dr-xr-xr-x  13 root root    0 Dec 22 13:24 sys
drwxrwxrwt   1 root root 4096 Mar 16  2021 tmp
drwxr-xr-x   1 root root 4096 Feb 22  2021 usr
drwxr-xr-x   1 root root 4096 Feb 22  2021 var
```

### Flag Bagian Kedua

Ini adalah bagian Kedua dari Flagnya jadi disimpan dulu
```bash
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
```

Lalu kita lanjutkan dengan mengikuti instruksinya
```bash
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~
ctf-player@pico-chall$ ls -la
total 32
drwxr-xr-x 1 ctf-player ctf-player 4096 Aug 13 16:24 .
drwxr-xr-x 1 root       root       4096 Mar 16  2021 ..
drwx------ 2 ctf-player ctf-player 4096 Aug 13 16:24 .cache
-rw-r--r-- 1 ctf-player ctf-player   80 Mar 16  2021 .profile
drw------- 1 ctf-player ctf-player 4096 Mar 16  2021 .ssh
-rw-r--r-- 1 ctf-player ctf-player   10 Mar 16  2021 3of3.flag.txt
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar 16  2021 drop-in
```

### Flag Terakhir

Dan ini Merupakan Akhir dari Flagnya
```bash
ctf-player@pico-chall$ cat 3of3.flag.txt
5190b070}
```

Jadi jika bila dibagungkan maka Flagnya adalah: picoCTF{xxsh_0ut_0f_\/\/4t3r_5190b070}


## References
