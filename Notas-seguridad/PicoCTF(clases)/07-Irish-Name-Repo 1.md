# Irish-Name-Repo 1
#picoCTF 
## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!

## Pistas 
+ There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
+ Try to think about how the website verifies your login.

## Solución
Al momento de inspeccionar el código fuente de la página nos damos cuenta de que hay un campo oculto, y cuando lo cambianos para que se vea podemos observar como realiza el SQL query al momento de intentar hacer login 
![html de la oágina](/PicoCTF(clases)/Capturas/Irish-Name-Repo-1.png)
Luego de ello se inserta una inyección sql y se logra obtener la bandera 
![html de la oágina](/PicoCTF(clases)/Capturas/Irish-Name-Repo-1(1).png)
## Bandera
picoCTF{s0m3_SQL_f8adf3fb}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
