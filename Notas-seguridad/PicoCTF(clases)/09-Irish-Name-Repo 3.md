# Reto
#picoCTF 
## Descripción
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!

## Pistas 
+ Seems like the password is encrypted.

## Solución
Para este reto la contraseña ha sido encriptada con el método rot 13, por lo que no se puede hacer una inyección como la del repo 1
![html de la oágina](/PicoCTF(clases)/Capturas/Irish-Name-Repo-3.png)
por lo que insertamos la contraseña encriptada para que al usarla en la query, funcione la inyección.
![html de la oágina](/PicoCTF(clases)/Capturas/Irish-Name-Repo-3(2).png)
## Bandera
picoCTF{3v3n_m0r3_SQL_7f5767f6}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
