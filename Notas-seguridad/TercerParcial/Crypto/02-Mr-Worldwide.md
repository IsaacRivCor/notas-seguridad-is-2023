# Mr-Worldwide
#picoCTF 
## Descripción
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

## Pistas 

## Solución
``` bash
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Mr-Worldwide]
└─$ wget https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
--2023-05-23 21:09:39--  https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 278 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[==============================================>]     278  --.-KB/s    in 0s      

2023-05-23 21:09:39 (5.47 MB/s) - ‘message.txt’ saved [278/278]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Mr-Worldwide]
└─$ ls
message.txt
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Mr-Worldwide]
└─$ file message.txt                                                                             
message.txt: ASCII text, with no line terminators
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Mr-Worldwide]
└─$ nano message.txt            
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Mr-Worldwide]
└─$ cat message.txt  
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Crypto/Mr-Worldwide]
└─$ 
```
Buscando las coordenadas que tiene el archivo de texto nos da una lista de lugares "Random", pero al tomar la primera letra de cada una de las ubicaciones, obtenermos la ciudad de kodiak de alaska

| coordenadas | Ciudad |
| ------------ | -------------- |
|(35.028309, 135.753082)| Kyoto, Japan
|(46.469391, 30.740883) | Odessa, Ukraine
|(39.758949, -84.191605) | Dayton, United States|
|(41.015137, 28.979530) | Istanbul, Turkey|
|(24.466667, 54.366669) | Abu Dhabi, UAE|
|(3.140853, 101.693207) | Kuala Lumpur, Malaysia|
|(9.005401, 38.763611) | Addis Ababa, Ethiopia|
|(-3.989038, -79.203560) | Loja, Ecuador|
|(52.377956, 4.897070) | Amsterdam, Netherlands|
|(41.085651, -73.858467) | Sleepy Hollow, USA|
|(57.790001, -152.407227) | Kodiak, United States|
|(31.205753, 29.924526) | Alexandria, Egypt|


## Bandera
picoCTF{KODIAK_ALASKA}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
