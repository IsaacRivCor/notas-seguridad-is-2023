# fixme1.py
#picoCTF 
## Descripción
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/38/fixme1.py)

## Pistas 
+ Indentation is very meaningful in Python
+ To view the file in the webshell, do: `$ nano fixme1.py`
+ To exit `nano`, press Ctrl and x and follow the on-screen prompts.
+ The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash
isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/38/fixme1.py
--2023-03-11 02:55:17--  https://artifacts.picoctf.net/c/38/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                       100%[======================================================>]     837  --.-KB/s    in 0s      

2023-03-11 02:55:18 (632 MB/s) - 'fixme1.py' saved [837/837]

isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu      README.txt  codebook.txt  file       flag      runme.py  static.ltdis.strings.txt  strings
Addadshashanammu.zip  code.py     convertme.py  fixme1.py  ltdis.sh  static    static.ltdis.x86_64.txt   warm
isaacrivcor-picoctf@webshell:~$ nano fixme1.py
isaacrivcor-picoctf@webshell:~$ python3 fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{1nd3nt1ty_cr1515_09ee727a}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
