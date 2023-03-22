# Cookies
#picoCTF 
## Descripción
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:64944/](http://mercury.picoctf.net:64944/)

## Pistas 
(None)

## Solución
```bash 
┌──(kali㉿kali)-[~]
└─$ for i in {1..20}; do curl -s http://mercury.picoctf.net:64944/check -H "Cookie: name=$i"; done | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}</code></p>
^C
                                                                             
┌──(kali㉿kali)-[~]
└─$ 

```
## Bandera
picoCTF{}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
