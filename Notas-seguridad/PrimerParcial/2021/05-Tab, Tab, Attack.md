# Tab, Tab, Attack
#picoCTF 
## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip)

## Pistas 
+ After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solución
```shell
isaacrivcor-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
--2023-03-09 03:41:32--  https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4521 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip            100%[======================================================>]   4.42K  --.-KB/s    in 0s      

2023-03-09 03:41:32 (1.59 GB/s) - 'Addadshashanammu.zip' saved [4521/4521]

isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu.zip  file  ltdis.sh  static.ltdis.strings.txt  strings
README.txt            flag  static    static.ltdis.x86_64.txt   warm
isaacrivcor-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu      README.txt  flag      static                    static.ltdis.x86_64.txt  warm
Addadshashanammu.zip  file        ltdis.sh  static.ltdis.strings.txt  strings
isaacrivcor-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-hay
-bash: cd: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-hay: No such file or directory
isaacrivcor-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ ls
fang-of-haynekhtnamet
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ cd fang-of-haynekhtnamet
-bash: cd: fang-of-haynekhtnamet: Not a directory
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ ls  
fang-of-haynekhtnamet
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ cd fang-of-haynekhtnamet
-bash: cd: fang-of-haynekhtnamet: Not a directory
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ cd fang-of-haynekhtnamet
-bash: cd: fang-of-haynekhtnamet: Not a directory
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ cd
isaacrivcor-picoctf@webshell:~$ ls
Addadshashanammu      README.txt  flag      static                    static.ltdis.x86_64.txt  warm
Addadshashanammu.zip  file        ltdis.sh  static.ltdis.strings.txt  strings
isaacrivcor-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ ls
fang-of-haynekhtnamet
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=47e898db922f38cb54ab4a08fb4e3def5a1cb6a1, not stripped
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ ls -la
total 12
drwxr-xr-x 2 isaacrivcor-picoctf isaacrivcor-picoctf   35 Mar 16  2021 .
drwxr-xr-x 3 isaacrivcor-picoctf isaacrivcor-picoctf   27 Mar 16  2021 ..
-rwxr-xr-x 1 isaacrivcor-picoctf isaacrivcor-picoctf 8320 Mar 16  2021 fang-of-haynekhtnamet
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
isaacrivcor-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularrad
allaku$ 
```
## Bandera
picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
