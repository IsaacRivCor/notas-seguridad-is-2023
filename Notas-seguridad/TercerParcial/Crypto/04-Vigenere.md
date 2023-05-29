# Vigenere
#picoCTF 
## Descripción
Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".

## Pistas 
+ https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher

## Solución
```bash 
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Vigenere]
└─$ wget https://artifacts.picoctf.net/c/158/cipher.txt 
--2023-05-23 21:47:40--  https://artifacts.picoctf.net/c/158/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.22, 13.249.74.17, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.69|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt                   100%[==============================================>]      43  --.-KB/s    in 0s      

2023-05-23 21:47:41 (34.4 MB/s) - ‘cipher.txt’ saved [43/43]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Vigenere]
└─$ ls
cipher.txt
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Vigenere]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Vigenere]
└─$ 
```
![[Vigenere.png]]
## Bandera
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae82272q}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
