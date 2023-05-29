# Bit-O-Asm-1
#picoCTF 
## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

## Pistas 
+ As with most assembly, there is a lot of noise in the instruction dump. Find the one line that pertains to this question and don't second guess yourself!

## Solución
``` bash
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-1]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2023-05-24 20:27:09--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.56, 13.249.74.17, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.69|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: ‘disassembler-dump0_a.txt’

disassembler-dump0_a.txt     100%[==============================================>]     209  --.-KB/s    in 0s      

2023-05-24 20:27:09 (86.8 MB/s) - ‘disassembler-dump0_a.txt’ saved [209/209]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-1]
└─$ ls
disassembler-dump0_a.txt
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-1]
└─$ nano disassembler-dump0_a.txt 
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-1]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/reversing/Bit-O-Asm-1]
└─$ python3 
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii(0x30)
'48'
>>> 
```
Al final de la ejecición la variable de la bandera o eax se queda con el valor 0x30
## Bandera
picoCTF{48}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
