# fixme2.py
#picoCTF 
## Descripción
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/67/fixme2.py)

## Pistas 
+ Are equality and assignment the same symbol?
+ To view the file in the webshell, do: `$ nano fixme2.py`
+ To exit `nano`, press Ctrl and x and follow the on-screen prompts.
+ The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash
isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/67/fixme2.py
--2023-03-11 03:01:23--  https://artifacts.picoctf.net/c/67/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                       100%[======================================================>]   1.00K  --.-KB/s    in 0s      

2023-03-11 03:01:23 (519 MB/s) - 'fixme2.py' saved [1029/1029]

isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu      code.py       file       flag      static                    strings
Addadshashanammu.zip  codebook.txt  fixme1.py  ltdis.sh  static.ltdis.strings.txt  warm
README.txt            convertme.py  fixme2.py  runme.py  static.ltdis.x86_64.txt
isaacrivcor-picoctf@webshell:~$ nano fixme2.py 
isaacrivcor-picoctf@webshell:~$ python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
