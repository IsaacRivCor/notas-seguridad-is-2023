# GDB Test Drive
#picoCTF 
## Descripción

Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/87/gdbme). Here's the test drive instructions:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`

## Pistas 
+ (None)

## Solución
```bash 
┌──(kali㉿kali)-[~/picoctf/reversing/GDBtestdrive]
└─$ wget https://artifacts.picoctf.net/c/87/gdbme                                                     
--2023-05-18 22:56:14--  https://artifacts.picoctf.net/c/87/gdbme
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.22, 13.249.74.17, 13.249.74.69, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17048 (17K) [application/octet-stream]
Saving to: ‘gdbme’

gdbme                        100%[==============================================>]  16.65K  --.-KB/s    in 0s      

2023-05-18 22:56:16 (34.1 MB/s) - ‘gdbme’ saved [17048/17048]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/GDBtestdrive]
└─$ ls
gdbme
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/GDBtestdrive]
└─$ chmod +x gdbme         
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/GDBtestdrive]
└─$ gdb gdbme         
GNU gdb (Debian 13.1-2) 13.1
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/GDBtestdrive]
└─$ 
```
![[GDBTestDrive.png]]
## Bandera
picoCTF{d3bugg3r_dr1v3_7776d758}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
