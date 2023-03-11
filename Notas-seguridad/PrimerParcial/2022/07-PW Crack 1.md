# PW Crack 1
#picoCTF 
## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/51/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/51/level1.flag.txt.enc) in the same directory too.

## Pistas 
+ To view the file in the webshell, do: `$ nano level1.py`
+ To exit `nano`, press Ctrl and x and follow the on-screen prompts.
+ The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash 
isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/51/level1.py 
--2023-03-11 03:09:43--  https://artifacts.picoctf.net/c/51/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                       100%[======================================================>]     876  --.-KB/s    in 0s      

2023-03-11 03:09:43 (334 MB/s) - 'level1.py' saved [876/876]

isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/51/level1.flag.txt.enc
--2023-03-11 03:10:00--  https://artifacts.picoctf.net/c/51/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.120, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc             100%[======================================================>]      30  --.-KB/s    in 0s      

2023-03-11 03:10:00 (13.6 MB/s) - 'level1.flag.txt.enc' saved [30/30]

isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu      code.py       file       flag                 ltdis.sh  static.ltdis.strings.txt  warm
Addadshashanammu.zip  codebook.txt  fixme1.py  level1.flag.txt.enc  runme.py  static.ltdis.x86_64.txt
README.txt            convertme.py  fixme2.py  level1.py            static    strings
isaacrivcor-picoctf@webshell:~$ nano level1.py
isaacrivcor-picoctf@webshell:~$ python3 level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{545h_r1ng1ng_56891419}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
