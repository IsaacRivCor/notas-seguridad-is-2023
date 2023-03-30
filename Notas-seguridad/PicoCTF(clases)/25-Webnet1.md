# Webnet1
#picoCTF 
## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Pistas 
+ Try using a tool like Wireshark. How can you decrypt the TLS stream?

## Solución
se abre el archivo de captura de paquetes y se inserta de nuevo la llave privada de este reto, y puedes extraer la imágen que se manda y al aplicarle un strngs obtienes la bandera
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/wbnet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2023-03-29 23:25:38--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                 100%[==============================================>]  90.36K  --.-KB/s    in 0.07s   

2023-03-29 23:25:39 (1.24 MB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensic/wbnet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2023-03-29 23:25:50--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                 100%[==============================================>]   1.66K  --.-KB/s    in 0s      

2023-03-29 23:25:50 (47.7 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensic/wbnet1]
└─$ ls
capture.pcap  picopico.key
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensic/wbnet1]
└─$ wireshark capture.pcap                                                                          
 ** (wireshark:47606) 23:27:40.593873 [GUI WARNING] -- FIX Add drag reordering to UAT dialog
 ** (wireshark:47606) 23:28:07.981948 [GUI WARNING] -- QXcbConnection: XCB error: 3 (BadWindow), sequence: 5593, resource id: 21675246, major code: 40 (TranslateCoords), minor code: 0
^C
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensic/wbnet1]
└─$ strings vulture.jpg -n15                                   
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensic/wbnet1]
└─$ 
```
### solución2 
se aplica el mismop filtro a los detalles de los paquetes como en el reto anterior o lo buscas siguiendo los strams TLS.
![[webNet1.png]]

## Bandera
picoCTF{honey.roasted.peanuts}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
