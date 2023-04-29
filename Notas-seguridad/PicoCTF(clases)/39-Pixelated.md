# Pixelated
#picoCTF 
## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)
## Pistas 
+ [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
+ Think of different ways you can "stack" images

## Solución
```bash 
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ wget https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png
--2023-04-27 14:37:08--  https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197176 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png               100%[==============================================>] 192.55K  21.3KB/s    in 9.0s    

2023-04-27 14:37:26 (21.3 KB/s) - ‘scrambled1.png’ saved [197176/197176]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ wget https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png
--2023-04-27 14:37:32--  https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197174 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png               100%[==============================================>] 192.55K  22.1KB/s    in 8.7s    

2023-04-27 14:37:50 (22.1 KB/s) - ‘scrambled2.png’ saved [197174/197174]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ ls
scrambled1.png  scrambled2.png
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ open scrambled1.png 
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ 
** (ristretto:15298): WARNING **: 14:39:02.707: (file.c:619):rstto_file_get_thumbnail: code should not be reached

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ ls
scrambled1.png  scrambled2.png
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ sudo apt install imagemagick
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
imagemagick is already the newest version (8:6.9.11.60+dfsg-1.6).
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ convert scrambled1.png -compose Add -composite flag.png
convert-im6.q16: image sequence is required `-composite' @ error/mogrify.c/MogrifyImageList/8003.
convert-im6.q16: no images defined `flag.png' @ error/convert.c/ConvertImageCommand/3229.
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ open flag.png
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ ls
scrambled1.png  scrambled2.png
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ convert scrambled1.png -compose Add -composite flag.png
convert-im6.q16: image sequence is required `-composite' @ error/mogrify.c/MogrifyImageList/8003.
convert-im6.q16: no images defined `flag.png' @ error/convert.c/ConvertImageCommand/3229.
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite flag.png 
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ open flag.png
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Pixelated]
└─$ 

```
![[flag (copy 1).png]]
## Bandera
picoCTF{d562333d}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
