# vault-door-3
#picoCTF 
## Descripción
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a648ca6dd275b9454c5d0de6d0f6efd3/VaultDoor3.java)

## Pistas 
+ Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.

## Solución
```bash
var password = 'jU5t_a_sna_3lpm18gb41_u_4_mfr340';
undefined
var buffer = Array(32)
undefined
for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);…
"g"

buffer.join("")

"jU5t_a_s1mpl3_an4gr4m_4_u_1fb380"
```
## Bandera
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_1fb380}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
