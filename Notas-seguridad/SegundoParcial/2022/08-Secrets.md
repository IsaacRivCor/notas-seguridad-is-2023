# Secrets
#picoCTF 
## Descripción
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:52025/).

## Pistas 
+ folders folders folders

## Solución
inspeccionando el código puedes notar que hay un directorio dentro llamado secrets 
![[Secrets.png]]
, ingresamos a ese directorio desde el navegador y dentro del código de esa página observamos que hay otro directorio llamado hidden
![[Secrets1.png]]
al cual si entramos desde el navegador vemos que es un login, y si inspeccionamos el código encontramos que hay otro directorio más llamado superhidden, al cual si entramos y seleccionamos todo el contenido de la página podemos encontrar la bandera
![[Secrets2.png]]
## Bandera
picoCTF{succ3ss_@h3n1c@10n_39849bcf}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
