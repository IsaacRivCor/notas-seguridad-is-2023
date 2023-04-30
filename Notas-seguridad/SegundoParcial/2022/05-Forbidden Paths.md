# Forbidden Paths
#picoCTF 
## Descripción
Can you get the flag? Here's the [website](http://saturn.picoctf.net:52278/). We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Pistas 
+ None

## Solución
al hacer la busqueda se hace con direcciones relativas usando 4 veces "../" para no tener que insertar el nombre de las carpetas y llegar sin problemas al archivo flag.txt
![[forbiddenpaths.png]]
![[forbiddenpaths2.png]]
## Bandera
picoCTF{7h3_p47h_70_5ucc355_6db46514}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
