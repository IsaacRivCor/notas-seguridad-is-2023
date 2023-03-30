# WebNet0
#picoCTF 
## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Pistas 
+ Try using a tool like Wireshark.
+ How can you decrypt the TLS stream?

## Solución
Se abre la captura de paquetes con wireshark, luego se carga la llave privada dentro de las prefereencias y el protocolo TLS para que se desencipten los paquetes, y al final se busca la cadena picoCTF dentro de los detalles de los paquetes

![[webNet0.png]]

### Solución 2
```bash ┌──(kali㉿kali)-[~/picoctf/forensic/wbnet0]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2
    61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67    ag: picoCTF{nong
    73 68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63    shim.shrimp.crac
    6b 65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c    kers}..Content-L
--
    67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73    g: picoCTF{nongs
    68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63 6b    him.shrimp.crack
    65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c 65    ers}..Content-Le
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensic/wbnet0]
└─$ 

```
## Bandera
picoCTF{nongshim.shrimp.crackers}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| ssldump -r [paquetes] -k [llavePrivada] | Herramienta que desencripta un archivo de captura de paquetes con una llave privada |

## Referencias
