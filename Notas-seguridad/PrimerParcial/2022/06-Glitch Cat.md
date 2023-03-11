# Glitch Cat
#picoCTF 
## Descripción
Our flag printing service has started glitching! $ nc saturn.picoctf.net 53933

## Pistas 
+ ASCII is one of the most common encodings used in programming
+ We know that the glitch output is valid Python, somehow!
+ Press Ctrl and c on your keyboard to close your connection and return to the command prompt.
## Solución
```bash
isaacrivcor-picoctf@webshell:~$ nc saturn.picoctf.net 53933
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
^C
isaacrivcor-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
'picoCTF{gl17ch_m3_n07_a4392d2e}'
>>> 
```

## Bandera
picoCTF{gl17ch_m3_n07_a4392d2e}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
