# Bandit Level 16 → Level 17
#bandit 
## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de acceso
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solución
```bash
bandit16@bandit:~$ nmap localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-02-23 18:14 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00015s latency).
Not shown: 994 closed ports
PORT      STATE SERVICE
22/tcp    open  ssh
1111/tcp  open  lmsocialserver
1840/tcp  open  netopia-vo2
4321/tcp  open  rwhois
8000/tcp  open  http-alt
30000/tcp open  ndmps

Nmap done: 1 IP address (1 host up) scanned in 0.22 seconds
bandit16@bandit:~$ nmap -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-02-23 18:17 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.0049s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.19 seconds
bandit16@bandit:~$ openssl s_client --connect localhost:31046
CONNECTED(00000003)
802B8AF7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
---
no peer certificate available
---
No client certificate CA names sent
---
SSL handshake has read 293 bytes and written 300 bytes
Verification: OK
---
New, (NONE), Cipher is (NONE)
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
bandit16@bandit:~$ openssl s_client --connect localhost:31518
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 21 22:03:57 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 21 22:03:57 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 21 22:02:57 2023 GMT; NotAfter: Feb 21 22:03:57 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEKgyQmjANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjIxMjIwMjU3WhcNMjMwMjIxMjIwMzU3WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDE
Ij2/8rREFcNp6D3KZMwYD8vHgn0sDSzZG4CDa2X2fwEbaY/oTQw8X6/WGLRftCfF
Tsaj9aKCy8tHYAlPwJZgK0gV7l1z1MlJGTdPcQbEkCwWmc0BF2yW/w/1w9GDIUf8
Cj7T5U2WZGjgw60NkWuzfvMLf852nnqVD2hnZP3VNDTaLYS0JdM+QikUBKutPqCV
WWxBixbgbb9lKHR/+OouJ7htNMzXcOyeUy1FHpC7vK22mtBJVWaolvSLH4+BWZVB
JtF/ltzwneXrpaQjL8smTDoc9MbYYReWo2hFGE5TRrWdvYnoJWs3ih2QR8t8RCTN
8tgIRE/hpRDnqpYcynGZAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAJ
+FLYSd/KC9V23BpaKvGsdR79r4VB5CamnArbcKACIthsIsP7OnKVHpcm/MoR9pDu
oTHQgwUFXE5hJnsGS9ecZbtGecKKyzFRCVUQJqLRHlVSsahfBWtepAzdYZ2IgVz0
v+bXUAfj4hFgD5Q2QGNhOpgWdaquNs2zOX2Z9NAy9jUk+9IiueNExN0Rl29llzc8
UVZW4j6UszuUv4FEA2AssMsabqc9EqPjUG7zeejvHi+rKYsEjLMfW/9sn0a9SJ7y
p2hhEOpGyj2Tkrikhe0+is6uxu8R06bkKB6BBzBAOq9GJtSQW8tzqSM1TGXyz6jT
DPOOoBL9IIjLJi8s1DBc
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 9E32A920CFA9179C63663B6BF8BA4869FD2FF448F304F3737E304A7B32CCFF59
    Session-ID-ctx:
    Resumption PSK: FA1ECBEF35F747C6D2D1FF77E9B9542E1BA7ED0EAFA79454033D02D5AA927661D1CA1B5F9CD2033335EAEE02A24A69C0
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 23 ef 0f 6d b3 b8 fb 95-0a ea 9b 21 59 e5 db 22   #..m.......!Y.."
    0010 - 29 16 71 8e ae 7c b0 87-f7 83 63 b4 04 c8 14 bd   ).q..|....c.....
    0020 - 0d bc 41 16 0b 92 c0 41-d3 9b de 3b 03 37 d8 05   ..A....A...;.7..
    0030 - c5 c5 16 73 dd a8 b9 b7-43 23 c6 11 8e 96 1d 1a   ...s....C#......
    0040 - 0c 70 89 8d 5d 38 08 f4-13 16 bd 6f 6f 59 6e 19   .p..]8.....ooYn.
    0050 - 28 80 7d 77 cf df ad 52-a2 66 cf 58 a9 39 b9 97   (.}w...R.f.X.9..
    0060 - 84 0c 3d b7 41 7b a2 b1-11 67 12 a1 c4 ba 78 b1   ..=.A{...g....x.
    0070 - ab 6b 64 d7 44 0b 31 8a-d0 8d a0 59 c1 d5 ae 9d   .kd.D.1....Y....
    0080 - c5 c8 32 ee 48 c0 2d 96-2a 72 07 4b d4 fa 4e f4   ..2.H.-.*r.K..N.
    0090 - a4 b5 76 53 03 d2 69 35-c2 f8 88 06 8c 1a c9 d7   ..vS..i5........
    00a0 - 6d fb cd ac 71 17 61 05-ee dc a8 12 75 cc 34 cf   m...q.a.....u.4.
    00b0 - 3d 57 76 bb f0 3e 4f dd-9f ae 47 55 f9 40 18 2b   =Wv..>O...GU.@.+
    00c0 - 96 de 0f 68 7f 01 bf 6e-e1 f2 31 d2 6e c7 06 a8   ...h...n..1.n...

    Start Time: 1677176387
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: B92EF63BAC2DB008050324D1E5DC380CD316DC2FF14160CF2974E05B3F5E9871
    Session-ID-ctx:
    Resumption PSK: 0417B5B0E5A41C22304A1EC65FA8A483E6E5DCC57CE833BF9DA4A11343FF42B726954E55BA3C66499E1748EBF03EA28B
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 23 ef 0f 6d b3 b8 fb 95-0a ea 9b 21 59 e5 db 22   #..m.......!Y.."
    0010 - 68 cd 7c 38 9e c4 84 05-c2 a6 98 6f c9 b8 3c ab   h.|8.......o..<.
    0020 - 8d b2 53 a9 42 9d 90 50-24 2d 78 41 f9 1e 3a f9   ..S.B..P$-xA..:.
    0030 - 9d 40 9e 60 5c 0a 79 32-f0 40 f6 c3 e9 56 15 00   .@.`\.y2.@...V..
    0040 - 96 f2 82 ad 24 f2 fd 75-3e 9d 8b b8 e7 98 e1 7b   ....$..u>......{
    0050 - 02 83 3e 6b 28 35 e3 d9-45 1a 44 b0 bb 4b 11 cf   ..>k(5..E.D..K..
    0060 - 8e 12 7b 2b ec d2 dd aa-a6 e6 06 7a 43 99 c0 a9   ..{+.......zC...
    0070 - 2c b7 53 ba d4 62 b2 d0-3e 52 2c e4 75 1e 0d 8e   ,.S..b..>R,.u...
    0080 - 60 60 83 bc 78 b0 21 40-b1 b1 fb a5 c1 dd e0 00   ``..x.!@........
    0090 - 12 28 3f bb dd eb d3 7e-0e 17 ca 59 5f f2 09 c9   .(?....~...Y_...
    00a0 - fd 40 27 44 e0 4e ca 24-a6 61 ad 31 fe 0c 70 39   .@'D.N.$.a.1..p9
    00b0 - 66 b9 35 95 cf 35 1c fa-2a d8 82 ee c2 10 a9 10   f.5..5..*.......
    00c0 - dd 26 14 ca 1d 3e ab c3-c6 13 3f 07 e4 ec e1 ab   .&...>....?.....

    Start Time: 1677176387
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
JQttfApK4SeyHwDlI9SXGR50qclOAil1
^C
bandit16@bandit:~$ openssl s_client --connect localhost:31691
CONNECTED(00000003)
802B8AF7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
---
no peer certificate available
---
No client certificate CA names sent
---
SSL handshake has read 293 bytes and written 300 bytes
Verification: OK
---
New, (NONE), Cipher is (NONE)
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
bandit16@bandit:~$ openssl s_client --connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 21 22:03:58 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 21 22:03:58 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 21 22:02:58 2023 GMT; NotAfter: Feb 21 22:03:58 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIELZxFNDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjIxMjIwMjU4WhcNMjMwMjIxMjIwMzU4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC8
C8jJ2//6TxiFBwjuC7+xUcu293V+n8pLxHfVnpZG9fvlOBG3nA3hm2/iNYybZNla
R58hZmfPWEKcuX7GZGvNUOAa6wOg2WYrMo1+6NCcynmCdJEabv2kemvOtBQFeV43
EUW+BW/+6903QuSHsjDewSoljGtmRGjg0oXUgyOlzGDQR/EfX7N8KGubYzZcHf+i
uZ35xMF5HQWi7Zf2ObapcbIfyjw2JWQLVqa8eDbZ4R4HKXYBLeJ4rZoYbPO1JUuX
IY6g+zV0yrgeX3EE36S4fYG/c5eixWRsA+KMYdJjtd2JTvEyyU9kSRQBNIJQOlmH
956MMGFmMqXn+kus9wgbAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCQ
ZF30iIq43MI9neBsmpAg3W5GsZzzV/JVOPDK1BG1ynEF5hqd6SFuRRSNXXy1AN3O
jL5m5B8sIh53vzfDBhv5XgSeKDm8KPqNn9CF5yP+neVglcJh3frf6DX4yE4yntHZ
SyxWErfMX/s5P1W4NdNoph6zNWBN5EjPls9mYo4gfkUnS72FDLfyGmPan8WKUP00
hhK6TdtbcetA/9HODOD2QL82tugZvCK9qPnNHG9TkcgaJ8LW9AY/ZCwnIYsODUQi
gYSDr2Ya4GuSAp2Vn4KkaJ1+NGmE+AxUMJ0rNsKUg6JelZ6vZ4TcFNbOSqaiCOtj
5xezGlZxL+dTerQ6hBwn
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 3444AA8940B7F56588A663947BA3140546402A82F0F2AB643EC5A5B140FA48D9
    Session-ID-ctx:
    Resumption PSK: 6ED91EA94783DFA1D7E715A83638F673F2A1D5B251C0544D07C93B457EB7EB22FF9A3AD3381AF25974EBDEFF78338B84
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - c6 5e 1a 4b fa 61 a1 cf-47 91 bc ee 77 38 8c 18   .^.K.a..G...w8..
    0010 - f1 36 58 c4 71 d8 10 bf-b5 04 12 a0 e6 69 5c c4   .6X.q........i\.
    0020 - ea 62 6e e3 cd 90 fb f8-7f b8 db a3 59 92 84 ec   .bn.........Y...
    0030 - e9 17 79 bf da 84 b8 0e-94 c1 1f 3b 9f 88 0a 89   ..y........;....
    0040 - 1b 6f 91 00 da 85 72 dd-c6 8a 05 c0 87 cc d6 c6   .o....r.........
    0050 - 1f a3 a5 71 d6 b3 ef da-c7 70 86 b2 30 87 3d 5f   ...q.....p..0.=_
    0060 - 97 d8 db b8 aa e4 39 ab-14 5b b0 95 b7 98 97 90   ......9..[......
    0070 - 14 45 e6 3e 3b 49 bd ee-f5 7e 24 90 7b 31 8c e5   .E.>;I...~$.{1..
    0080 - df 1c 87 94 a1 aa c6 c4-bb 4f 76 c8 f2 a4 a6 9a   .........Ov.....
    0090 - 36 37 ea b9 1c ce 1e b1-85 af 45 47 84 5e de fa   67........EG.^..
    00a0 - 40 4e 8a d0 18 65 98 55-3a 72 63 98 4e a6 2e ef   @N...e.U:rc.N...
    00b0 - 65 aa d2 f2 57 19 7c 42-be 71 7e 92 fa 8a a8 fd   e...W.|B.q~.....
    00c0 - 04 46 08 13 52 44 0b e7-53 ba c2 a7 0e 96 3d 4a   .F..RD..S.....=J

    Start Time: 1677176479
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: BF8F7C7846F6C304D87EA6EA5A2D6EFCD6084E7818E6B098A7623383FBC82D6D
    Session-ID-ctx:
    Resumption PSK: F69BEDC1C3D4822F8C44E0A8822824F60FDE161B8EB0AE9707F947A8939A76B17AAE95429A80D7350AD03543662D013F
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - c6 5e 1a 4b fa 61 a1 cf-47 91 bc ee 77 38 8c 18   .^.K.a..G...w8..
    0010 - 04 57 fb ed 0c 97 85 5c-67 89 c3 73 13 2a 1c 83   .W.....\g..s.*..
    0020 - 2e ee 0c 30 26 66 8d 1b-35 68 db 11 75 8e 00 7f   ...0&f..5h..u...
    0030 - dc 00 9a 5d 3d 4b a6 31-2c 22 c6 7e 28 16 d0 27   ...]=K.1,".~(..'
    0040 - 13 35 04 10 4d 25 3b 55-7d ae 3f 12 81 f3 d7 fa   .5..M%;U}.?.....
    0050 - fa 2b 18 7e 7f 80 c2 62-ef 28 74 96 67 5a dd 49   .+.~...b.(t.gZ.I
    0060 - 34 45 94 d2 fa 8b 36 d9-ef f3 47 bd 6b f4 2c ca   4E....6...G.k.,.
    0070 - 40 98 9f 1f b3 70 e0 8e-fd d9 71 35 23 a8 2e ef   @....p....q5#...
    0080 - 88 66 65 a1 29 fa 9e 22-e2 76 77 44 92 32 d3 17   .fe.)..".vwD.2..
    0090 - 5c b3 f5 6d b7 56 34 27-7b 47 68 fb 92 f3 96 e4   \..m.V4'{Gh.....
    00a0 - e4 0c a3 2a 17 11 4b 19-d4 e3 86 8c 36 cb 1d 1a   ...*..K.....6...
    00b0 - 0c 46 fa 1d f7 76 2b 9d-1f 21 e7 19 b9 81 10 80   .F...v+..!......
    00c0 - be 0b 8b e5 b1 87 23 2c-be a5 d6 d2 19 dd 99 00   ......#,........

    Start Time: 1677176480
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed

```
## Notas adicionales
| comando | descripción |
|----------|----------|
|nmap|escaner de puertos abiertos|
|-p|parametro para buscar entre un rango de puertos|

## Referencias
