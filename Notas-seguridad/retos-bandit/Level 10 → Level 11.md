# Bandit Level 10 → Level 11
#bandit #base64
## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Datos de acceso
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución
``` bash
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$

```
## Notas adicionales
| comando | descripción |
|----------|----------|
|base64|encripta una frase en base64|
| -d | desencripta un archivo que esté en base64|

## Referencias
[base64](https://ubunlog.com/base64-codificacion-decodificacion-terminal/)