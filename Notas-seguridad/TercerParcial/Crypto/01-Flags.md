# Flags
#picoCTF 
## Descripción
What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?

## Pistas 
+ The flag is in the format PICOCTF{}

## Solución
```bash 
┌──(kali㉿kali)-[~/TercerParcial/Crypto]
└─$ mkdir Flags   
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto]
└─$ cd Flags   
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Flags]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
--2023-05-23 20:58:41--  https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43257 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png                     100%[==============================================>]  42.24K  --.-KB/s    in 0.003s  

2023-05-23 20:58:42 (15.3 MB/s) - ‘flag.png’ saved [43257/43257]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Flags]
└─$ ls
flag.png
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Flags]
└─$ open flag.png 
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Flags]
└─$ 
```
![[TercerParcial/CapturasTercerParcial/flag.png]]
Haciendo una busqueda por internet, encuentras que las banderas en la imágen dada por el reto, son banderas marítimas, y cada una reprecenta una letra, por lo que solo hay que reemplazar la bandera por la letra que corresponde.
![[TercerParcial/CapturasTercerParcial/flag1.png]]
![[flag2.png]]![[TercerParcial/CapturasTercerParcial/flag3.png]]
## Bandera
PICOCTF{F1AG5AND5TUFF}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
https://en.wikipedia.org/wiki/International_maritime_signal_flags