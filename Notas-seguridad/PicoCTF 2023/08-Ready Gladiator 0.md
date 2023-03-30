# Ready Gladiator 0

## Descripcion

Can you make a CoreWars warrior that always loses, no ties? Your opponent is the Imp. The source is available [here](https://artifacts.picoctf.net/c/309/imp.red). If you wanted to pit the Imp against himself, you could download the Imp and connect to the CoreWars server like this: `nc saturn.picoctf.net 55776 < imp.red`
## Pistas
(None)
## Solucion 
```bash
 ┌──(alexia㉿alexHM)-[~/Downloads]
└─$ cat imp.red
;redcode
;name Imp Ex
;assert 1
mov 0,1

end                                                                    ┌──(alexia㉿alexHM)-[~/Downloads]
└─$ vim imp.red

┌──(alexia㉿alexHM)-[~/Downloads]
└─$ cat imp.red
;redcode
;name Imp Ex
;assert 1
mov 0,0

end



                                                                                                      
┌──(alexia㉿alexHM)-[~/Downloads]
└─$ nc saturn.picoctf.net 54791 < imp.red
;redcode
;name Imp Ex
;assert 1
mov 0,0

end

Submit your warrior: (enter 'end' when done)

Warrior1:
;redcode
;name Imp Ex
;assert 1
mov 0,0

end

Rounds: 100
Warrior 1 wins: 0
Warrior 2 wins: 100
Ties: 0
You did it!
picoCTF{h3r0_t0_z3r0_4m1r1gh7_f1e207c4}


```
## Bandera
picoCTF{h3r0_t0_z3r0_4m1r1gh7_f1e207c4}

## Notas Adicionales 

