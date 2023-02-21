# Bandit Level 12 → Level 13
#bandit 
## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solución
``` bash
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ cat data.txt | xxd -r
��
 �cdata2.bin<��BZh91AY&SY��q����Y�ůc���s����|�����������������;,YA�dz�@�hi�h4dz���4��hѠɦ����'�=OI�i��=@�����=F��CA�4��z��<��z�hy@�
�@z��h44�d�hb�Ŭ��j��v��y�TfSW#w�Iڃ`��ȔC��   �pUf���zSVG($�����ZK(&*��nkxM�����j�S��$�:|�ہҺ/��[�ӕ�>2���ұ)P�&���>ڗ����~��@��A�xo���3<�
����OB�ݤ�����O��"C[f�ўH��Q,-֤�V��(� a�l�^��˔�"�a0hVe��I/����q%p[��B&
X��e
    ��VHﹰ#
T*���ܑN$#-}�9��}<bandit12@bandit:~$ R} �L�Mk����4��d��T�mg��GB���--��ĥzE^-�DξO
bandit12@bandit:~$ cat data.txt | xxd -r | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Wed Jan 11 19:18:38 2023, max compression, from Unix
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Wed Jan 11 19:18:38 2023, max compression, from Unix
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | tar xO | bzcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Wed Jan 11 19:18:38 2023, max compression, from Unix
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:~$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|xxd|hace un vaciado exadecimal de un archivo|
|-r|revierte el vaciado exadecimal|
|bzcat|descomprime en memoria un archivo bzip2|
|zcat|descomprime en memoria un archivo gzip|
|tar xO|descomprime en memoria un archivo tar|

## Referencias
