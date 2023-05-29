# transposition-trial
#picoCTF 
## Descripción
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).

## Pistas 
+ Split the message up into blocks of 3 and see how the first block is scrambled

## Solución
```bash
┌──(kali㉿kali)-[~/TercerParcial/Crypto/transposition-trial]
└─$ wget https://artifacts.picoctf.net/c/193/message.txt                                           
--2023-05-23 21:29:37--  https://artifacts.picoctf.net/c/193/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.17, 13.249.74.56, 13.249.74.22, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.17|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[==============================================>]      54  --.-KB/s    in 0s      

2023-05-23 21:29:38 (13.7 MB/s) - ‘message.txt’ saved [54/54]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/transposition-trial]
└─$ ls
message.txt
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/transposition-trial]
└─$ nano message.txt
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/transposition-trial]
└─$ cat message.txt
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/transposition-trial]
└─$ 
```
![[transpotitionTrial.png]]
## Bandera
picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
