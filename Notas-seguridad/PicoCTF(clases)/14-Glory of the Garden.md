### Glory of the Garden
#picoCTF 
## Descripción
This [garden](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contains more than it seems.

## Pistas 
+ What is a hex editor?

## Solución
``` bash
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ strings garden.jpg -n 20   
Copyright (c) 1998 Hewlett-Packard Company
IEC http://www.iec.ch
IEC http://www.iec.ch
.IEC 61966-2.1 Default RGB colour space - sRGB
.IEC 61966-2.1 Default RGB colour space - sRGB
,Reference Viewing Condition in IEC61966-2.1
,Reference Viewing Condition in IEC61966-2.1
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
Here is a flag "picoCTF{more_than_m33ts_the_3y3657BaB2C}"
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ 


```
## Bandera
picoCTF{more_than_m33ts_the_3y3657BaB2C}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| hexeditor | abre un archivo e un editoe hexadecimal |

## Referencias
