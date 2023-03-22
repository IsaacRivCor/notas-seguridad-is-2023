# GET aHEAD
#picoCTF 
## Descripción
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

## Pistas 
+ Maybe you have more than 2 choices
+ Check out tools like Burpsuite to modify your requests and look at the responses

## Solución
Inpeccionamos lá página y cambiamos el metodo en el que pedimos la informacidon de POST a HEAD y en la repspuesta del navegador nos da la bandera
![html de la oágina](/PicoCTF(clases)/Capturas/GET-aHead.png)![html de la oágina](/PicoCTF(clases)/Capturas/GET-aHead(1).png)

## Bandera
picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
