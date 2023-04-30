# Wireshark doo dooo do doo..
#picoCTF 
## Descripción
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng).

## Pistas 
+ None

## Solución
al abrir el paquete de captura y seguir los paquetes TCP, em el 5to stream vemos una linea con la estructura de una bandera, y si la pasamos por cyberchef, nos la decodifica de rot13 y nos da la bandera
![[wiresharkdoodoodoo.png]]
![[wiresharkdoodoodoo1.png]]
## Bandera
picoCTF{p33kab00_1_s33_u_deadbeef}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
