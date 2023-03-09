# First Grep
#picoCTF 
## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Pistas 
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución
```shell 
isaacrivcor-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
--2023-03-09 02:32:04--  https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file'

file                            100%[======================================================>]  14.21K  --.-KB/s    in 0s      

2023-03-09 02:32:04 (364 MB/s) - 'file' saved [14551/14551]

isaacrivcor-picoctf@webshell:~$ ls  
README.txt  file  strings
isaacrivcor-picoctf@webshell:~$ file file 
file: ASCII text, with very long lines (4200)
isaacrivcor-picoctf@webshell:~$ grep 'pico' file 
picoCTF{grep_is_good_to_find_things_dba08a45}
isaacrivcor-picoctf@webshell:~$ ^C
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{grep_is_good_to_find_things_dba08a45}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
