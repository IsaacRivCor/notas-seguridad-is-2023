# Bandit Level 18 → Level 19
#bandit 
## Objetivo
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

## Datos de acceso
bandit18
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Solución
```bash
PS C:\Users\isaac> ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
PS C:\Users\isaac>

```
```bash
PS C:\Users\isaac> ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
id
uid=11018(bandit18) gid=11018(bandit18) groups=11018(bandit18)
ls
readme
cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

```
## Notas adicionales
| comando | descripción |
|----------|----------|
|xx|xx|

## Referencias
