# Codebook
#picoCTF 
## Descripción
Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/101/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/101/codebook.txt)

## Pistas 
+ On the webshell, use `ls` to see if both files are in the directory you are in
+ The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash 
isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/101/code.py
--2023-03-11 02:52:43--  https://artifacts.picoctf.net/c/101/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                         100%[======================================================>]   1.25K  --.-KB/s    in 0s      

2023-03-11 02:52:43 (490 MB/s) - 'code.py' saved [1278/1278]

isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/101/codebook.txt
--2023-03-11 02:52:51--  https://artifacts.picoctf.net/c/101/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.120, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                    100%[======================================================>]      27  --.-KB/s    in 0s      

2023-03-11 02:52:52 (13.0 MB/s) - 'codebook.txt' saved [27/27]

isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu      README.txt  codebook.txt  file  ltdis.sh  static                    static.ltdis.x86_64.txt  warm
Addadshashanammu.zip  code.py     convertme.py  flag  runme.py  static.ltdis.strings.txt  strings
isaacrivcor-picoctf@webshell:~$ python3 code.py 
picoCTF{c0d3b00k_455157_7d102d7a}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{c0d3b00k_455157_7d102d7a}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
