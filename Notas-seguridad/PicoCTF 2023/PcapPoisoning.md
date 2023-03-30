## Descripción
How about some hide and seek heh? Download this [file](https://artifacts.picoctf.net/c/374/trace.pcap) and find the flag.

## Solución
Descargar el archivo trace, abrir y analizar los paquetes, seleccionar el protocolo DNS, seguir su secuencia UDP y seleccionar la opcion filtrar secuencia, seleccionar el protocolo FTP y realizar seguimiento TCP. La bandera se encuentra en el protocolo TCP.

```bash

0000   45 00 00 52 00 01 00 00 40 06 c3 90 ac 10 00 02   E..R....@.......
0010   0a fd 00 06 00 14 00 15 00 00 00 00 00 00 00 00   ................
0020   50 02 20 00 d7 21 00 00 70 69 63 6f 43 54 46 7b   P. ..!..picoCTF{ 
0030   50 36 34 50 5f 34 4e 34 4c 37 53 31 53 5f 53 55   P64P_4N4L7S1S_SU				
0040   35 35 33 35 35 46 55 4c 5f 34 36 32 34 61 38 62   55355FUL_4624a8b
0050   36 7d                                             6}

```

## Notas Adicionales
|comando|descripcion|
|---|---|
|xx|xx|

## Referencias
- []()

