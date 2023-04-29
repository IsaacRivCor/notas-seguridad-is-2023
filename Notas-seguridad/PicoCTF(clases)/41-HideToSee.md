# HideToSee
#picoCTF 
## Descripción
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).

## Pistas 
+ Download the image and try to extract it.

## Solución
```bash 
┌──(kali㉿kali)-[~/picoctf/crypto/HideToSee]
└─$ wget https://artifacts.picoctf.net/c/235/atbash.jpg 
--2023-04-27 15:11:52--  https://artifacts.picoctf.net/c/235/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.119, 18.160.124.108, 18.160.124.38, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.119|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51499 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                   100%[=============================================>]  50.29K  --.-KB/s    in 0.09s   

2023-04-27 15:12:00 (576 KB/s) - ‘atbash.jpg’ saved [51499/51499]

                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/crypto/HideToSee]
└─$ ls
atbash.jpg
```
![[atbash.jpg]]
```bash
┌──(kali㉿kali)-[~/picoctf/crypto/HideToSee]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/HideToSee]
└─$ ls
atbash.jpg  encrypted.txt
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/HideToSee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_92533667}
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/HideToSee]
└─$ 
!```
![[atbashsolution.png]]
## Bandera
picoCTF{atbash_crack_92533667}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
