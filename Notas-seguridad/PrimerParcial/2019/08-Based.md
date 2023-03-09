# Based
#picoCTF 
## Descripción
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.

## Pistas 
+ I hear python can convert things.
+ It might help to have multiple windows open.

## Solución
```shell 
isaacrivcor-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
lizard
Please give the 01101100 01101001 01111010 01100001 01110010 01100100 as a word.
...
you have 45 seconds.....

Input:
lizard
Please give me the  154 151 155 145 as a word.
Input:
lime
Please give me the 6c616d70 as a word.
Input:
lamp
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
```
**Converciones hechas en cyberchef**

## Bandera
picoCTF{learning_about_converting_values_00a975ff}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
+ [Cyberchef primera palabra](https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=MDExMDExMDAgMDExMDEwMDEgMDExMTEwMTAgMDExMDAwMDEgMDExMTAwMTAgMDExMDAxMDA) 
+ [Cyberchef segunda palabra](https://gchq.github.io/CyberChef/#recipe=From_Octal('Space')&input=MTU0IDE1MSAxNTUgMTQ1)
+ [Cyberchef tercera palabra](https://gchq.github.io/CyberChef/#recipe=From_Hex('None')&input=NmM2MTZkNzA) 