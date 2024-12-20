# 1_wanna_b3_a_r0ck5tar

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)

## Challenge information
```
Tags: picoCTF 2019, General Skills, Medium
Author: ALEX BUSHKIN

Description:
The Rockstar language has changed since this problem was released! 
Use this Wayback Machine URL to use an older version of Rockstar, here.

Hints:
(None)
```
Challenge link: [https://play.picoctf.org/practice/challenge/82](https://play.picoctf.org/practice/challenge/82)

## Solution

Mulai dari mengecek isi dari file `lyrics.txt`
```bash
┌──(kali㉿kali)-[/mDownloads]
└─$ cat lyrics.txt 
Rocknroll is right              
Silence is wrong                
A guitar is a six-string        
Tommy's been down               
Music is a billboard-burning razzmatazz!
Listen to the music             
If the music is a guitar                  
Say "Keep on rocking!"                
Listen to the rhythm
If the rhythm without Music is nothing
Tommy is rockin guitar
Shout Tommy!                    
Music is amazing sensation 
Jamming is awesome presence
Scream Music!                   
Scream Jamming!                 
Tommy is playing rock           
Scream Tommy!       
They are dazzled audiences                  
Shout it!
Rock is electric heaven                     
Scream it!
Tommy is jukebox god            
Say it!                                     
Break it down
Shout "Bring on the rock!"
Else Whisper "That ain't it, Chief"                 
Break it down   
```

Jika saya mencoba menjalankan program di [online emulator](https://web.archive.org/web/20190522020843/https://codewithrockstar.com/online) Saya mendapatkan jendela popup yang mengharapkan masukan. Memasukkan sesuatu seperti `test` tidak menghasilkan keluaran apa pun.

Lalu saya mencoba mempelajari [language documentation](https://codewithrockstar.com/docs).

Menelusuri skrip baris demi baris memberikan saya pemahaman tentang apa yang terjadi
```
Rocknroll is right                                      # Tidak perlu, karena variabel tidak digunakan nanti  
Silence is wrong                                        # Tidak perlu, karena variabel tidak digunakan nanti  
A guitar is a six-string                                # A guitar = 19 (tidak perlu, Karena tidak akan dioutput)
Tommy's been down                                       # Tommy = 44 (tidak perlu, Karena tidak akan dioutput)
Music is a billboard-burning razzmatazz!                # Music = ??? (tidak perlu, Karena tidak akan dioutput)
Listen to the music                                     # Input to music variable (tidak perlu)          
If the music is a guitar                                # Comparison (tidak perlu)
Say "Keep on rocking!"                                  # Print "Keep on rocking!" (tidak perlu)
Listen to the rhythm                                    # Input to rhythm variable (tidak perlu)
If the rhythm without Music is nothing                  # Comparison (tidak perlu)
Tommy is rockin guitar                                  # Tommy = 66
Shout Tommy!                                            # Output Tommy, i.e. 66
Music is amazing sensation                              # Music = 79
Jamming is awesome presence                             # Jamming = 78
Scream Music!                                           # Output Music, i.e. 79
Scream Jamming!                                         # Output Jamming, i.e. 78
Tommy is playing rock                                   # Tommy = 74
Scream Tommy!                                           # Output Tommy, i.e. 74
They are dazzled audiences                              # Tommy = 79
Shout it!                                               # Output Tommy, i.e. 79
Rock is electric heaven                                 # Rock = 86
Scream it!                                              # Output rock, i.e. 86
Tommy is jukebox god                                    # Tommy = 73
Say it!                                                 # Output Tommy, i.e. 73
Break it down
Shout "Bring on the rock!"
Else Whisper "That ain't it, Chief"                 
Break it down 
```

Kemudian saya menghapus kode yang tidak digunakan dan membersihkan skrip ke versi minimal seperti ini
```
Tommy is rockin guitar
Shout Tommy
Music is amazing sensation
Jamming is awesome presence
Scream Music
Scream Jamming
Tommy is playing rock
Scream Tommy
Cajac is dazzled audiences
Shout Cajac 
Rock is electric heaven
Scream Rock
Tommy is jukebox god
Say Tommy
```

Kemudian menjalankan kode ini di emulator akan menghasilkan keluaran ini
```
66
79
78
74
79
86
73
```
Bisa diliat ini adalah angka ascii

Jadi Saya langsung saja menggunakan ASCII to Text Converter[Duplichecker.com](https://www.duplichecker.com/ascii-to-text.php)

![image](https://github.com/user-attachments/assets/3b750970-db02-4df6-b415-32f35e3c9579)

Jadi Flagnya: picoCTF{BONJOVI}

## References

- [Rockstar](https://esolangs.org/wiki/Rockstar)
- [Rockstar Online Emulator](https://web.archive.org/web/20190522020843/https://codewithrockstar.com/online)
- [Wikipedia - ASCII](https://en.wikipedia.org/wiki/ASCII)
