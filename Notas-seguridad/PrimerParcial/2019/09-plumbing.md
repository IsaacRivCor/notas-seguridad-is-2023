# plumbing
#picoCTF 
## Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.

## Pistas 
+ Remember the flag format is picoCTF{XXXX}
+ What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html) 

## Solución
```shell
isaacrivcor-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 | grep pico -
picoCTF{digital_plumb3r_06e9d954}
^C
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{digital_plumb3r_06e9d954}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
