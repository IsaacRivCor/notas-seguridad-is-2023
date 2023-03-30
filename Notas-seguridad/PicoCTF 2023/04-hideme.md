# hideme

## Descripcion
Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/488/flag.png).

## Pistas
(None)

## Solucion 
```bash
                                                                                
┌──(alexia㉿alexHM)-[~/Downloads]
└─$ exiftool flag.png 
ExifTool Version Number         : 12.57
File Name                       : flag.png
Directory                       : .
File Size                       : 43 kB
File Modification Date/Time     : 2023:03:14 12:35:48-06:00
File Access Date/Time           : 2023:03:14 12:35:52-06:00
File Inode Change Date/Time     : 2023:03:14 12:35:48-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 512
Image Height                    : 504
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Warning                         : [minor] Trailer data after PNG IEND chunk
Image Size                      : 512x504
Megapixels                      : 0.258
                                                                                
┌──(alexia㉿alexHM)-[~/Downloads]
└─$ unzip flag.png
Archive:  flag.png
warning [flag.png]:  39739 extra bytes at beginning or within zipfile
  (attempting to process anyway)
   creating: secret/
  inflating: secret/flag.png         
                                                                                
┌──(alexia㉿alexHM)-[~/Downloads]
└─$ ls    
docker-desktop-4.17.0-amd64.deb  enc_flag  flag.png  secret
      
┌──(alexia㉿alexHM)-[~/Downloads]
└─$ cd secret   
                                                                                
┌──(alexia㉿alexHM)-[~/Downloads/secret]
└─$ ls
flag.png                  
```

![[flag.png]]
## Bandera
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_5fbf3ff9}

## Notas Adicionales 
|comando|descripcion|
|---|---|
|exiftool|xx|
