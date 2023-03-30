# Reto
#picoCTF 
## Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) is all blank!

## Pistas 
None

## Solución
``` bash
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ wget https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
--2023-03-28 14:25:41--  https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2964 (2.9K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt      100%[================>]   2.89K  --.-KB/s    in 0s      

2023-03-28 14:25:49 (49.6 MB/s) - ‘whitepages.txt’ saved [2964/2964]

                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ ls
whitepages.txt
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ file whitepages.txt 
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1376), with no line terminators
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ wc whitepages.txt 
   0    0 2964 whitepages.txt
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ xxd -l 32 whitepages.txt 
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ cat whitepages.txt 
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ sed 's/ /0/g' whitepages.txt   
0000 0 00000 00 0000 00 0   00000  0 00 0  000  0  0    0 0000  0 0 0 000 000  00000 0 00000 0 00000 00 0000 00 0 0 00  0 000 0 0 000 0 00 000000 0 00000 0 0 0 0 0000 00 00  000 00 00 0 0000  00 000000 0 00 00 000 0 0 0000  0 00    0 0 00 00 000 000 0 00  00 0000000 00  000 000000 0000 00 00000 0 0000  0 00 0  0 000   0 0 00 00 00    0 0 0 0 0 00   00 000 0000 000000 0 00 00 000 0 0 0 00000 00    0 0 00 00 0 0 000000 0 00000 00 0000 00 00  0 0 00  000000  000000  000000 000000 000  00  0    0   00 00  000 00  00 0 0   00  00 000000 00000 0   0  00  00 0 00 0  0000 000000 0 00000  0 00 0   0 000   0 000   00  0  000 00   0 0 0   00 00  00   0  0 00000 0  0000 000000 0 00000 00000 00 0000000  000 00  0 0 00  00 000  000 00  00  0000 0 00000 00 0000 00 0   00000  0 00 0  000  0  0    0 0000  0 0 0 000 000  00    0  0  0   00  0    0   0 000 0     0  0000 0  0  000  0  000 0     0   00  0   00000  0000 0  000  0  00 0 0   00  0 0     0  0000 0   00 00  00 0 0 0     0  000  0   00 00  00 0 0  0000 0   0 000  00 0 0  00 000 0     0  00 0 0   000 0   0 0 0  0000 0  0  000 0     0  000  00  0 0 00  0 000  00  000  00 000  0   0  000  0  00 0000  000000  0 0 0  000  00  00 000  000 00   00000   00 0  00  000   00000  000 00  0 0000  0   0  000  0  000  00  0  00  00  000  0 0 0  00 000  00 0 0  000 000  00 00  00 0 00  0 0 00  0  00     0 0000 0 00000 00 0000 00                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ sed 's/ /0/g' whitepages.txt | sed 's/ /1/g'
00001010000010010000100101110000011010010110001101101111010000110101010001000110000010100000101000001001000010010101001101000101010001010010000001010000010101010100001001001100010010010100001100100000010100100100010101000011010011110101001001000100010100110010000000100110001000000100001001000001010000110100101101000111010100100100111101010101010011100100010000100000010100100100010101010000010011110101001001010100000010100000100100001001001101010011000000110000001100000010000001000110011011110111001001100010011001010111001100100000010000010111011001100101001011000010000001010000011010010111010001110100011100110110001001110101011100100110011101101000001011000010000001010000010000010010000000110001001101010011001000110001001100110000101000001001000010010111000001101001011000110110111101000011010101000100011001111011011011100110111101110100010111110110000101101100011011000101111101110011011100000110000101100011011001010111001101011111011000010111001001100101010111110110001101110010011001010110000101110100011001010110010001011111011001010111000101110101011000010110110001011111011000110011010100110100011001100011001000110111011000110110010000110000001101010110001100110010001100010011100000111001011001100011100000110001001101000011011101100011011000110011011001100110001101010110010001100101011000100011001001100101001101010011011001111101000010100000100100001001                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$   
```
conversión de ese vinario en cyberchef : picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}
## Bandera
picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| sed | busca los caracteres y los cambia por los que se pasen como parametro |

## Referencias
