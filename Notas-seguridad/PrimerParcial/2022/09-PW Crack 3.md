# PW Crack 3
#picoCTF 
## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/24/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/24/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/24/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Pistas 
+ To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
+ To exit `bvi` type `:q` and press enter.
+ The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash 
isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/24/level3.py
--2023-03-11 03:18:22--  https://artifacts.picoctf.net/c/24/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                       100%[======================================================>]   1.31K  --.-KB/s    in 0s      

2023-03-11 03:18:22 (416 MB/s) - 'level3.py' saved [1337/1337]

isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/24/level3.flag.txt.enc
--2023-03-11 03:18:29--  https://artifacts.picoctf.net/c/24/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.120, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc             100%[======================================================>]      31  --.-KB/s    in 0s      

2023-03-11 03:18:30 (10.9 MB/s) - 'level3.flag.txt.enc' saved [31/31]

isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/24/level3.hash.bin
--2023-03-11 03:18:37--  https://artifacts.picoctf.net/c/24/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                 100%[======================================================>]      16  --.-KB/s    in 0s      

2023-03-11 03:18:37 (6.80 MB/s) - 'level3.hash.bin' saved [16/16]

isaacrivcor-picoctf@webshell:~$ bvi level3.hash.bin

bvi version 1.4.0 Copyright (C) 1996-2014 by Gerhard Buergmann
isaacrivcor-picoctf@webshell:~$ bvi level3.hash.bin

bvi version 1.4.0 Copyright (C) 1996-2014 by Gerhard Buergmann
isaacrivcor-picoctf@webshell:~$ nanlo level3.py
-bash: nanlo: command not found
isaacrivcor-picoctf@webshell:~$ nano level3.py
isaacrivcor-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: f09e
That password is incorrect
isaacrivcor-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 4dcf
That password is incorrect
isaacrivcor-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 87ab
That password is incorrect
isaacrivcor-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: dba8
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{m45h_fl1ng1ng_cd6ed2eb}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
