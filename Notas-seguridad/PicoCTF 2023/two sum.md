## Descripción
Can you solve this? What two positive numbers can make this possible: n1 > n1 + n2 OR n2 > n1 + n2

## Solución
Aprovechar de las limitaciones de Integer, al ser el número máximo 2,147,483,647 al agregar 1, se genera un ovelflow el número se vuelve negativo -2,147,483,647.

```bash

alberto@Nova:~$ nc saturn.picoctf.net 60817
n1 > n1 + n2 OR n2 > n1 + n2 
What two positive numbers can make this possible: 
2147483647 1
You entered 2147483647 and 1
You have an integer overflow
YOUR FLAG IS: picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_f6ed8057}

exit

```

## Notas Adicionales
|comando|descripcion|
|---|---|
|xx|xx|

## Referencias
- []()

