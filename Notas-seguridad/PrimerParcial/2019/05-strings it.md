# strings it

## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?

## Pistas 
[strings](https://linux.die.net/man/1/strings)

## Solución
```bash
isaacrivcor-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
--2023-03-02 19:03:59--  https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                                                   100%[==================================================================================================================================>] 757.84K  1.85MB/s    in 0.4s    

2023-03-02 19:03:59 (1.85 MB/s) - 'strings' saved [776032/776032]

isaacrivcor-picoctf@webshell:~$ file strings
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=047a5079a5f563cd0e540d28f42a37161093ffda, not stripped
isaacrivcor-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_827aee91}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{5tRIng5_1T_827aee91}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| wget | navegador en linea de texto, puedes descargar archivos |

## Referencias
