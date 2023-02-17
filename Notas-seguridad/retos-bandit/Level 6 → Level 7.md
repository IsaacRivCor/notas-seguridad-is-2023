# Bandit Level 6 → Level 7
#bandit #file 
## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

-   owned by user bandit7
-   owned by group bandit6
-   33 bytes in size

## Datos de acceso
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Solución
``` bash
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|-user|filtra por usuario|
| -group | filtra por grupo|
| 2 | salida de error |
| > | manda la salida a otro lugar|

## Referencias
