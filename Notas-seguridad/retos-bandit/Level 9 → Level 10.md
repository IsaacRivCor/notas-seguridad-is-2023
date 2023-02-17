# Bandit Level 9 → Level 10
#bandit #strings
## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solución
``` bash
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
c========== the
h;========== password
========== isT
n.E========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|strings|muestra las secuencias de caracrteres imprimibles de almenos 4 caracteres|

## Referencias
