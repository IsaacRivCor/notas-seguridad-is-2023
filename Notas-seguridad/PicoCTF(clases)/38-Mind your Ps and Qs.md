# Mind your Ps and Qs 
#picoCTF 
## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)

## Pistas 
+ Bits are expensive, I used only a little bit over 100 to save money

## Solución
```bash 
──(kali㉿kali)-[~/picoctf/crypto/Minyour]
└─$ wget https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values               
--2023-04-27 14:18:58--  https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 205 [application/octet-stream]
Saving to: ‘values’

values                       100%[==============================================>]     205  --.-KB/s    in 0s      

2023-04-27 14:19:13 (188 MB/s) - ‘values’ saved [205/205]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Minyour]
└─$ ls
values
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/Minyour]
└─$ cat values    
Decrypt my super sick RSA:
c: 421345306292040663864066688931456845278496274597031632020995583473619804626233684
n: 631371953793368771804570727896887140714495090919073481680274581226742748040342637
e: 65537  
```
![[MindYourPsandQs.png]]
```python
┌──(kali㉿kali)-[~]
└─$ python           
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import inverse, long_to_bytes
>>> p = 1461849912200000206276283741896701133693
>>> q = 431899300006243611356963607089521499045809
>>> n = 631371953793368771804570727896887140714495090919073481680274581226742748040342637
>>> p * q == n
True
>>> tn = (p-1) * (q-1)
>>> e = 65537
>>> c = 421345306292040663864066688931456845278496274597031632020995583473619804626233684
>>> d = inverse(e,tn)
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639647889241102700065917
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_55304594}'
>>> 

```
## Bandera
picoCTF{sma11_N_n0_g0od_55304594}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
