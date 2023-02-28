# Bandit Level 17 → Level 18
#bandit 
## Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

## Datos de acceso
bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

## Solución
```bash
bandit17@bandit:~$ ls
passwords.new  passwords.old
bandit17@bandit:~$ wc passwords.new
 100  100 3300 passwords.new
bandit17@bandit:~$ wc passwords.old
 100  100 3300 passwords.old
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< f9wS9ZUDvZoo3PooHgYuuWdawDFvGld2
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$

```
## Notas adicionales
| comando | descripción |
|----------|----------|
|diff|compara dos archivos linea por linea|

## Referencias
