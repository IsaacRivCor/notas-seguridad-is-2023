# Reto
#picoCTF 
## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Pistas 
none

## Solución
Se obtiene la bandera con un script de python que se obtiene con los 3 últimos dígitos del puerto origen desde el stream 32 al 60
```python
from scapy.all import * 

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:  
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)

print(flag)

```

``` bash
┌──(kali㉿kali)-[~/picoctf/forensic/sharkonwire2]
└─$ python exp.py 
picoCTF{p1LLf3r3d_data_v1a_st3g0}
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/sharkonwire2]
└─$ 

```

## Bandera
picoCTF{p1LLf3r3d_data_v1a_st3g0}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
