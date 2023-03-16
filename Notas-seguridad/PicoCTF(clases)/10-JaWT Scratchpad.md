# JaWT Scratchpad 
#picoCTF 
## Descripción
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090

## Pistas 
+ What is that cookie?
+ Have you heard of JWT?

## Solución
dentro de la página tienes que hacer login conc ualquier usuario excepto como admin, por lo que hacemos login con cualquier usuario y la revisar las cookies podemos observar que nos genera un token jwt, y con la página de jwt.io modificamos el usuario como admin, pero eso no es necesario ya que el token necesita un password especifico para generar el token. por lo que con una herramienta de kali llamada john the ripper obtenermos la contraseña, que resultó ser ilovepico, y con ello en la página de jwt.io obtenemos el nuevo token con el que entraremos como admin en la página del repo.
![html de la oágina](/PicoCTF(clases)/Capturas/JaWT-Scratchpad.png)
![html de la oágina](/PicoCTF(clases)/Capturas/JaWT-Scratchpad(2).png)

## Bandera
picoCTF{jawt_was_just_what_you_thought_f859ab2f}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
