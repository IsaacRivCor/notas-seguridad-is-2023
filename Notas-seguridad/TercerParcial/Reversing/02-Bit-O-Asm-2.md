# Bit-O-Asm-2
#picoCTF 
## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

## Pistas 
+ `PTR`'s or 'pointers', reference a location in memory where values can be stored.

## Solución
``` bash
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-2]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2023-05-24 20:36:18--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.56, 13.249.74.17, 13.249.74.22, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.56|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt     100%[==============================================>]     270  --.-KB/s    in 0s      

2023-05-24 20:36:19 (117 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-2]
└─$ ls
disassembler-dump0_b.txt
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-2]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-2]
└─$ python3
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii(0x9fe1a)
'654874'
>>> 
```
Al final de la ejecición la variable de la bandera o eax se queda con el valor 0x9fe1a
## Bandera
picoCTF{654874}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
