# Bandit Level 20 → Level 21
#bandit 
## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## Datos de acceso
bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solución
```bash 
bandit20@bandit:~$ nc -nlvp 1843 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 3121321
bandit20@bandit:~$ Listening on 0.0.0.0 1843

bandit20@bandit:~$ ./suconnect 1843
Connection received on 127.0.0.1 53028
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -nlvp 1843 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|jobs|muestra las tareas en backgrpund|
|&|manda el proceso al background|
## Referencias
