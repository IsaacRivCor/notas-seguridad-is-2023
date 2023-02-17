# Bandit Level 2 → Level 3
#bandit 
## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Datos de acceso
bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Solución
```bash
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```
## Notas adicionales
- Cuando hay espacios en el nombre hay que delimitarlo.
## Referencias
