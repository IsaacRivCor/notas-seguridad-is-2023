# Bandit Level 8 → Level 9
#bandit #sort #uniq
## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Datos de acceso
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Solución
``` bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
 1001  1001 33033 data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|sort |ordena el contenido de un archivo|
| uniq | muestra una sola vez las cadenas no repetidas
| -u | muestra las cadenas que no se repiten |

## Referencias
