# Local Authority
#picoCTF 
## Descripción
Can you get the flag? Go to this [website](http://saturn.picoctf.net:55983/) and see what you can discover.

## Pistas 
+ How is the password checked on this website?

## Solución
Al inspeccional el código de la página se puede observer que hay un archivo llamado login.php, en el que si entras encuentras encuentras algunas validaciónes, pero lo inportante está dentro del archivo llamado secure.js, en donde se encuentra la validación (con usuario y contraseña) para poder hacer login, una vez hecho login te dan la bandera.
![[LocalAuthority.png]]
![[LocalAuthority2.png]]
## Bandera
picoCTF{j5_15_7r4n5p4r3n7_a8788e61}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
