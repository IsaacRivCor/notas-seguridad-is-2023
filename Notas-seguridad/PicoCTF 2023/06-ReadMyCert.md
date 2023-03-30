# ReadMyCert

## Descripcion
How about we take you on an adventure on exploring certificate signing requests Take a look at this CSR file [here](https://artifacts.picoctf.net/c/378/readmycert.csr).

## Pistas
Download the certificate signing request and try to read it.

## Solucion 
```bash
openssl req -text -noout -verify -in readmycert.csr 
Certificate request self-signature verify OK
Certificate Request:
    Data:
        Version: 1 (0x0)
        Subject: CN = picoCTF{read_mycert_e675addc}, name = ctfPlayer
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:d5:d0:1d:57:bd:53:77:cb:cb:da:e0:07:28:b5:
                    93:35:bb:09:7b:b3:82:ae:a4:ee:2c:bf:db:c0:13:
                    db:4f:a9:fc:b3:7e:d0:19:74:f7:90:37:80:db:99:
                    06:9f:da:7f:f2:a3:7c:19:ef:ed:0c:22:07:7e:6e:
                    78:88:19:21:26:99:f0:fe:9e:38:de:b6:f0:e3:7b:
                    13:64:c9:e9:c0:1e:79:9f:d1:0b:43:cc:1d:44:c3:
                    7e:70:61:7b:81:6f:e2:5b:a2:83:c3:73:1c:4d:76:
                    38:f9:1f:55:87:e0:19:23:8c:61:96:04:48:50:6d:
                    05:e5:77:e7:0a:d2:11:3e:26:f2:e4:9c:cd:20:6f:
                    be:b6:6e:80:86:f6:df:ca:26:25:67:e8:7b:53:c2:
                    2e:a4:83:a3:3a:f1:b4:b4:92:ad:33:71:c4:84:9a:
                    a6:56:b2:8a:d7:63:d7:0c:f1:c5:22:ce:50:3c:86:
                    7c:c4:54:29:bc:32:b5:f1:6c:90:91:3f:89:fb:09:
                    02:df:4e:88:08:52:0f:12:57:06:b4:88:4e:3b:08:
                    f2:2b:79:4b:3b:be:de:bd:f5:c4:b5:4a:c4:29:f4:
                    3b:dc:cf:db:fb:a3:93:e9:e7:4b:2f:1e:65:5f:23:
                    40:2d:c1:07:fd:61:f7:32:c5:f5:68:fe:b0:24:a2:
                    1b:af
                Exponent: 65537 (0x10001)
        Attributes:
            Requested Extensions:
                X509v3 Extended Key Usage: 
                    TLS Web Client Authentication
    Signature Algorithm: sha256WithRSAEncryption
    Signature Value:
        01:54:38:c7:a9:3f:f9:3d:fa:2d:bf:d4:d4:e4:2e:e3:11:39:
        95:12:b2:68:06:f9:26:32:3c:c6:5f:7d:31:e1:7b:8d:af:9e:
        b8:4c:c5:5b:59:f3:14:78:4b:25:19:dd:df:98:a3:29:a3:32:
        4d:70:7e:6c:f0:aa:dc:c7:56:5a:b8:c5:8b:04:50:3f:0c:c5:
        88:e4:2c:6d:8c:40:8c:37:9f:06:02:c6:e3:e5:3f:37:90:00:
        9d:92:a8:68:b9:c0:8f:06:f4:49:f3:94:a1:17:ce:b0:f8:ab:
        f6:49:45:90:27:c9:c6:59:a9:b5:ee:50:60:1c:04:ae:bd:3f:
        ae:0d:62:fe:cd:dd:8c:06:48:47:f4:99:48:bb:23:ed:97:88:
        23:23:15:2e:66:6c:71:10:41:bd:94:96:f2:3c:1f:c8:9a:9f:
        72:b4:08:fa:1d:e2:05:22:d0:0a:34:17:90:76:0b:0b:7a:ec:
        d8:62:3e:f0:28:30:b9:9d:ea:a6:3d:de:07:2b:66:50:95:ec:
        8f:12:10:1f:a8:42:56:ee:2b:3b:a5:48:35:89:47:fe:d0:3f:
        18:ac:4f:49:fe:c6:45:b2:c6:a4:b0:ac:e1:c5:e9:7d:96:fb:
        3a:54:a2:c6:1c:88:54:f9:20:88:f8:a7:6d:e6:08:c0:16:a6:
        b3:db:5b:d3


```
## Bandera
picoCTF{read_mycert_e675addc}

## Notas Adicionales 
https://pleasantpasswords.com/info/pleasant-password-server/b-server-configuration/3-installing-a-3rd-party-certificate/openssl-commands
