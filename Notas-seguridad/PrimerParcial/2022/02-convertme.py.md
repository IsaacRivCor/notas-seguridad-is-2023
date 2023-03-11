# convertme.py
#picoCTF 
## Descripción
Run the Python script and convert the given number from decimal to binary to get the flag.

## Pistas 
+ Look up a decimal to binary number conversion app on the web or use your computer's calculator!
+ The `str_xor` function does not need to be reverse engineered for this challenge.
+ If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
+ To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
+ Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
+ Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`

## Solución
```bash 
isaacrivcor-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/30/convertme.py
--2023-03-11 02:50:13--  https://artifacts.picoctf.net/c/30/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                    100%[======================================================>]   1.16K  --.-KB/s    in 0.001s  

2023-03-11 02:50:13 (1.15 MB/s) - 'convertme.py' saved [1189/1189]

isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu      README.txt    file  ltdis.sh  static                    static.ltdis.x86_64.txt  warm
Addadshashanammu.zip  convertme.py  flag  runme.py  static.ltdis.strings.txt  strings
isaacrivcor-picoctf@webshell:~$ python3 convertme.py
If 53 is in decimal base, what is it in binary base?
Answer: 110101
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{4ll_y0ur_b4535_762f748e}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
