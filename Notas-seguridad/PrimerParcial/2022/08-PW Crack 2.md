# PW Crack 2
#picoCTF 
## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level2.flag.txt.enc) in the same directory too.

## Pistas 
+ Does that encoding look familiar?
+ The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash
isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level2.py
--2023-03-11 03:12:51--  https://artifacts.picoctf.net/c/17/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                       100%[======================================================>]     914  --.-KB/s    in 0s      

2023-03-11 03:12:51 (544 MB/s) - 'level2.py' saved [914/914]

isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level2.flag.txt.enc
--2023-03-11 03:13:06--  https://artifacts.picoctf.net/c/17/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.74, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc             100%[======================================================>]      31  --.-KB/s    in 0s      

2023-03-11 03:13:06 (12.1 MB/s) - 'level2.flag.txt.enc' saved [31/31]

isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu      codebook.txt  fixme2.py            level2.flag.txt.enc  static                    warm
Addadshashanammu.zip  convertme.py  flag                 level2.py            static.ltdis.strings.txt
README.txt            file          level1.flag.txt.enc  ltdis.sh             static.ltdis.x86_64.txt
code.py               fixme1.py     level1.py            runme.py             strings
isaacrivcor-picoctf@webshell:~$ nano level12.py
isaacrivcor-picoctf@webshell:~$ nano level2.py
isaacrivcor-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
'4ec9'
>>> 
isaacrivcor-picoctf@webshell:~$ python3 level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{tr45h_51ng1ng_9701e681}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
