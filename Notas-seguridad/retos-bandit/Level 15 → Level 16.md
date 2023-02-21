# Bandit Level 15 → Level 16
#bandit 
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
```bash
bandit15@bandit:~$  openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 21 06:20:29 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 21 06:20:29 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 21 06:19:29 2023 GMT; NotAfter: Feb 21 06:20:29 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEA7qUdzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjIxMDYxOTI5WhcNMjMwMjIxMDYyMDI5WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDL
vM0gZzAHdXTeD5t4ruUJo/kRs4UAodA9XcqDhNtW464W0c55RqKLp921syy3Lvjr
8Q9WkqvCFX+efShMd8XnzbT/dyRrD+cZQnSiPJ3bwDdpwqfkl9h3mb609Kb5HI6R
JgogEyuRLJI+HKtr/wXHwo1vBZ0+yaPMX6sdkd6Hu5Ra0L5Q5+E5+3F/8QgvCeVE
hDRIOrh2a7jxykb8G6+xVC6jIZY0YfrZz6LrESyQau256pqyaQPqQoUWTlitxIql
Ym2Baw7vYDxmFZrvj0FkumC6NokX6K2G9bZ0DaKR/DspPdAC4oT81SawJvsBibdN
51VI6dxBn412ZS8bS155AgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQA9
skxWNwZbedjaVTa5yMPUZQ4Nf5/LAAMtS5Q7mzGH5tdQsTGR0Z4n4eA4hzrmzHBF
MVRL5mR9n+sM5pIrKDa6f4zIc5ObxDyN19ie+3SFASCPz9tihK8Js2V8qsR6LHV1
pfD8DSG0hZPtUuK3Mfi+nWqQUFiiTGj30mb9vlS1sSWv5PGznou1gQ3ZfrDs7B4K
ZKZrllPIVV1CrlDw2Bv8Dc432LQuZAmKAjBd6FG0OAboU/WJMTwAfVjlKMtvC8tg
DZ3djSTprq6PrXlI0utw/MsMIh69b61BRXUuDvRxhU11SNmSI8aegjVL8KuK+Euh
sSLPTocV29SY1YXOwEQi
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
    Session-ID: 626587617B3CC90BE673892AADAC691477916B66FA8F88F121F6C4B06C3D6230
    Session-ID-ctx:
    Resumption PSK: 82A937768C273FEFCCAA9C34B0AD51376686796B8E202389170AE42397DD1A75102AC2AE546970D17CE4F33099C5C962
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ee ae 09 e4 56 06 6c 9e-c9 80 86 77 50 83 15 59   ....V.l....wP..Y
    0010 - 8b 2f 41 1d f8 92 07 3b-ef 7a 8f 3a 79 6f cd 97   ./A....;.z.:yo..
    0020 - fd 1d 18 44 55 be 6d 69-90 69 87 0c 8e e6 cf 39   ...DU.mi.i.....9
    0030 - eb a3 21 b2 4d 94 51 6d-5f 1c b3 bc 76 79 07 5e   ..!.M.Qm_...vy.^
    0040 - 17 d5 97 85 8b e9 17 40-4b 0b f1 a6 69 18 57 bf   .......@K...i.W.
    0050 - 9a 8f 3b de 34 07 f2 d5-20 c8 37 df ab 22 d8 48   ..;.4... .7..".H
    0060 - 02 a8 b0 ed 7c 87 61 bd-40 3f 0f 62 8b 7e d7 36   ....|.a.@?.b.~.6
    0070 - d9 fb e4 4e 89 20 d2 1f-3b 0b 6e e7 8a 2c 44 18   ...N. ..;.n..,D.
    0080 - 01 93 66 41 43 ba 04 84-59 f9 78 fe 88 b5 1e b5   ..fAC...Y.x.....
    0090 - 1b d2 86 a0 81 e1 ad a5-74 a0 7c 5b fa e7 d1 e2   ........t.|[....
    00a0 - 5e c5 3b c4 b7 b8 5c b4-8e 1d af b9 52 c5 99 4c   ^.;...\.....R..L
    00b0 - 38 37 1d a1 19 1e ad aa-8f 1f 04 ae 59 33 84 62   87..........Y3.b
    00c0 - 2d ab dc 0e a8 ae dc 52-7c 2c aa 19 09 97 60 a6   -......R|,....`.

    Start Time: 1677007524
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
    Session-ID: DCF34FA6FCF7675907A37D2BB4E5FEEA086685C9E61038DF4DE63B6AEAEDAB6A
    Session-ID-ctx:
    Resumption PSK: A765254AC7428975DC943C1C151E0C68421B4C92A59CE7E61BE137C1FA3333FFBB07D0253895331C46CA2782F9CF5835
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ee ae 09 e4 56 06 6c 9e-c9 80 86 77 50 83 15 59   ....V.l....wP..Y
    0010 - eb a0 df a6 c3 00 85 e7-14 2b 92 0b d1 3d cf dc   .........+...=..
    0020 - 7f 99 5d 57 d5 73 73 d2-e1 c1 7c e7 96 8b 78 53   ..]W.ss...|...xS
    0030 - e8 94 79 4c fe 8d 61 87-36 57 b9 da 68 48 72 56   ..yL..a.6W..hHrV
    0040 - de 69 6e 9b 22 56 1f c6-3b 9f 04 01 e3 d4 35 72   .in."V..;.....5r
    0050 - 77 1c ba 3d c3 ed 0d 73-11 a7 22 cf 57 48 93 42   w..=...s..".WH.B
    0060 - 8a 2d 5d 59 46 10 e2 54-c9 e8 56 23 70 e0 9d b9   .-]YF..T..V#p...
    0070 - 5b 80 f5 f7 bc ea 38 f5-26 8f fe 06 48 0d f8 70   [.....8.&...H..p
    0080 - 1c be 5b 2c a4 0d e7 31-a7 d0 7b d4 41 2d 81 78   ..[,...1..{.A-.x
    0090 - 81 e9 26 14 a4 18 11 b4-49 b2 ff 3d 22 3b b7 cf   ..&.....I..=";..
    00a0 - c1 67 31 57 b9 c4 3b a0-35 4b 59 7b 74 dd 32 40   .g1W..;.5KY{t.2@
    00b0 - 03 82 e9 de 07 c4 b9 fe-27 47 91 56 56 dd 7d eb   ........'G.VV.}.
    00c0 - 9d 7d 06 51 d6 30 e9 fa-64 8b 89 7a 05 d2 06 aa   .}.Q.0..d..z....

    Start Time: 1677007524
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|openssl|cliente ssl|
|s_client|cliente para conectarse|

## Referencias
