# Redaction gone wrong
#picoCTF 
## Descripción
Now you DON’T see me. This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Pistas 
+ How can you be sure of the redaction?

## Solución
```bash
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/redactiongonewrong]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2023-04-29 22:55:16--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.22, 13.249.74.17, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.69|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_for_ABC_Lab 100%[=============================================>]  34.10K  --.-KB/s    in 0.006s  

2023-04-29 22:55:16 (5.49 MB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

                                                                                                                   
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/redactiongonewrong]
└─$ ls
Financial_Report_for_ABC_Labs.pdf
                                                                                                                   
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/redactiongonewrong]
└─$ pdftotext Financial_Report_for_ABC_Labs.pdf         
                                                                                                                    
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/redactiongonewrong]
└─$ ls
Financial_Report_for_ABC_Labs.pdf  Financial_Report_for_ABC_Labs.txt
                                                                                                                    
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/redactiongonewrong]
└─$ cat Financial_Report_for_ABC_Labs.txt 
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.

Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document.


                                                                                                                    
┌──(kali㉿kali)-[~/SegundoParcial/Forensic/redactiongonewrong]
└─$ 

```
## Bandera
picoCTF{C4n_Y0u_S33_m3_fully}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| pftrotext | permite extraer el contenido de un archivo pdf a un archivo de texto |

## Referencias
