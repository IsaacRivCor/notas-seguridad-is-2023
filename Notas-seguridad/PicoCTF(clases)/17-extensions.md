# extensions
#picoCTF 
## Descripción
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Pistas 
+ How do operating systems know what kind of file it is? (It's not just the ending!
+ Make sure to submit the flag as picoCTF{XXXXX}

## Solución
se cambia la extención del archivo para poder abrirlo como una imágen
``` bash      
┌──(kali㉿kali)-[~/picoctf/forensic/extensions]
└─$ file flag.txt 
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/extensions]
└─$ mv flag.txt flag.png
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/extensions]
└─$ open flag.png 
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/extensions]
└─$ 
** (ristretto:20215): WARNING **: 14:39:35.743: (file.c:619):rstto_file_get_thumbnail: code should not be reached

```
![html de la oágina](/PicoCTF(clases)/Capturas/flag.png)
## Bandera
picoCTF{now_you_know_about_extensions}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
