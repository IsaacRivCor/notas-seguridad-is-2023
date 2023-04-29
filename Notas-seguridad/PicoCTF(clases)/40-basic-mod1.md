# basic-mod1
#picoCTF 
## Descripción
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/127/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Pistas 
+ Do you know what `mod 37` means?
+ `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solución
```bash 
┌──(kali㉿kali)-[~/picoctf/crypto]
└─$ mkdir basic-mode1                                                                      
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto]
└─$ cd basic-mode1 
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/basic-mode1]
└─$ wget https://artifacts.picoctf.net/c/127/message.txt
--2023-04-27 14:53:58--  https://artifacts.picoctf.net/c/127/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.34, 18.160.124.108, 18.160.124.119, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.34|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 85 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[==============================================>]      85  --.-KB/s    in 0.008s  

2023-04-27 14:54:07 (10.5 KB/s) - ‘message.txt’ saved [85/85]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/basic-mode1]
└─$ ls
message.txt
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/basic-mode1]
└─$ cat message.txt 
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140                                                                                                                     
┌──(kali㉿kali)-[~/picoctf/crypto/basic-mode1]
└─$ python exp.py
R0UND_N_R0UND_79C18FB3
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/basic-mode1]
└─$ 

```
Sript de python
```python
datos = open('message.txt').read().split()

flag = ''
for n in datos: 
        c = int(n) % 37
        if c >= 0 and c <= 25:
                s = chr(c+65)  
        elif c >= 26 and c <= 35:
                s = chr(c+22)
        else:
                s = '_'
        flag += s

print(flag)

```

## Bandera
picoCTF{R0UND_N_R0UND_79C18FB3}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
