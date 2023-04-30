# Lookey here
#picoCTF 
## Descripción
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/124/anthem.flag.txt).

## Pistas 
+ Download the file and search for the flag based on the known prefix.

## Solución
```bash
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/lookeyhere]
└─$ wget https://artifacts.picoctf.net/c/124/anthem.flag.txt 
--2023-04-29 22:44:41--  https://artifacts.picoctf.net/c/124/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.56, 13.249.74.69, 13.249.74.17, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.56|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt              100%[=============================================>] 106.12K  --.-KB/s    in 0.09s   

2023-04-29 22:44:42 (1.12 MB/s) - ‘anthem.flag.txt’ saved [108668/108668]

                                                                                                                   
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/lookeyhere]
└─$ ls
anthem.flag.txt
                                                                                                                   
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/lookeyhere]
└─$ cat anthem.flag.txt 
      ANTHEM

      by Ayn Rand


        CONTENTS

         PART ONE

         PART TWO

         PART THREE

         PART FOUR

         PART FIVE

         PART SIX

         PART SEVEN

         PART EIGHT

         PART NINE

         PART TEN

         PART ELEVEN

         PART TWELVE
...

┌──(kali㉿kali)-[~/SegundoParcial/Forensic/lookeyhere]
└─$ grep "picoCTF{.*}" anthem.flag.txt 
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}
                                                                                                                   
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/lookeyhere]
└─$ 
```

## Bandera
picoCTF{gr3p_15_@w3s0m3_4c479940}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
