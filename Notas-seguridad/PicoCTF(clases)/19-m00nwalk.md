# m00nwalk
#picoCTF 
## Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.

## Pistas 
+ How did pictures from the moon landing get sent back to Earth?
+ What is the CMU mascot?, that might help select a RX option

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ wget https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav
--2023-03-28 14:10:27--  https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav         100%[================>]  10.55M  1.03MB/s    in 7.5s    

2023-03-28 14:10:43 (1.41 MB/s) - ‘message.wav’ saved [11066998/11066998]

                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ ls
extensions  garden.jpg  message.wav  sharkonwire1  someta  whatlieswithin
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ sstv -d message.wav -o flag.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [###########################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ ls
extensions  garden.jpg   sharkonwire1  whatlieswithin
flag.png    message.wav  someta
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ 

```
![[flag.png]]
## Bandera
picoCTF{beep_boop_im_in_space}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| sstv -d [auidio] -o [imagen] | script en python para decodificar el audio y convertirlo en una fotoo |

## Referencias
