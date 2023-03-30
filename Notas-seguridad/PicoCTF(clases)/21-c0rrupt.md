# Reto
#picoCTF 
## Descripción
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Pistas 
+ Try fixing the file header

## Solución
```bash 
──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery       
--2023-03-28 14:40:04--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 202940 (198K) [application/octet-stream]
Saving to: ‘mystery’

mystery             100%[================>] 198.18K   478KB/s    in 0.4s    

2023-03-28 14:40:14 (478 KB/s) - ‘mystery’ saved [202940/202940]

                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ ls
mystery
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ file mystery       
mystery: data
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ exiftool mystery   
ExifTool Version Number         : 12.57
File Name                       : mystery
Directory                       : .
File Size                       : 203 kB
File Modification Date/Time     : 2020:10:26 14:30:20-04:00
File Access Date/Time           : 2023:03:28 14:40:21-04:00
File Inode Change Date/Time     : 2023:03:28 14:40:14-04:00
File Permissions                : -rw-r--r--
Error                           : Unknown file type
                                                                                 
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ xxd -l 32 mystery       
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ hexeditor mystery     
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ file mystery 
mystery: data
                                                                                 
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ exiftool mystery
ExifTool Version Number         : 12.57
File Name                       : mystery
Directory                       : .
File Size                       : 203 kB
File Modification Date/Time     : 2023:03:28 14:43:28-04:00
File Access Date/Time           : 2023:03:28 14:43:33-04:00
File Inode Change Date/Time     : 2023:03:28 14:43:28-04:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Warning                         : PNG image did not start with IHDR
SRGB Rendering                  : Perceptual
Gamma                           : 2.2
Pixels Per Unit X               : 2852132389
Pixels Per Unit Y               : 5669
Pixel Units                     : meters
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ hexeditor mystery
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ sudo apt install pngcheck                   
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  pngcheck
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 68.5 kB of archives.
After this operation, 208 kB of additional disk space will be used.
Get:1 http://kali.download/kali kali-rolling/main amd64 pngcheck amd64 3.0.3-1 [68.5 kB]
Fetched 68.5 kB in 38s (1,821 B/s)                                          
Selecting previously unselected package pngcheck.
(Reading database ... 393406 files and directories currently installed.)
Preparing to unpack .../pngcheck_3.0.3-1_amd64.deb ...
Unpacking pngcheck (3.0.3-1) ...
Setting up pngcheck (3.0.3-1) ...
Processing triggers for man-db (2.11.2-1) ...
Processing triggers for kali-menu (2023.1.7) ...
                                                                             
 203  hexeditor mystery
  204  open mystery
  205  pngcheck -v mystery
  206  hexeditor mystery
  207  pngcheck -v mystery
  208  hexeditor mystery
  209  pngcheck -v mystery
  210  hexeditor mystery
  211  pngcheck -v mystery
  212  open mystery
```
Se repararon los "magic bits" y los primeros chucks de uuna imagen para poder abrirla y obtener la bandera que tiene dentro.
![[mystery.png]]
## Bandera
picoCTF{c0rrupt10n_1847995}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
