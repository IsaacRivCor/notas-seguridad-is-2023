# reverse_cipher
#picoCTF 
## Descripción
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this). Can you reverse the flag.

## Pistas 
+ objdump and Gihdra are some tools that could assist with this

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ wget https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev
--2023-05-18 23:06:43--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16856 (16K) [application/octet-stream]
Saving to: ‘rev’

rev                          100%[==============================================>]  16.46K  --.-KB/s    in 0s      

2023-05-18 23:06:44 (59.8 MB/s) - ‘rev’ saved [16856/16856]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ wget https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
--2023-05-18 23:06:50--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24 [application/octet-stream]
Saving to: ‘rev_this’

rev_this                     100%[==============================================>]      24  --.-KB/s    in 0s      

2023-05-18 23:06:51 (57.1 MB/s) - ‘rev_this’ saved [24/24]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ ls
rev  rev_this
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ file rev           
rev: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=523d51973c11197605c76f84d4afb0fe9e59338c, not stripped
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ file rev_this 
rev_this: ASCII text, with no line terminators
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ cat rev_this      
picoCTF{w1{1wq85jc=2i0<}                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ cat rev_this | wc
      0       1      24
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ objdump -D rev -M intel | grep '<main>:' -A50           
0000000000001185 <main>:
    1185:       55                      push   rbp
    1186:       48 89 e5                mov    rbp,rsp
    1189:       48 83 ec 50             sub    rsp,0x50
    118d:       48 8d 35 74 0e 00 00    lea    rsi,[rip+0xe74]        # 2008 <_IO_stdin_used+0x8>
    1194:       48 8d 3d 6f 0e 00 00    lea    rdi,[rip+0xe6f]        # 200a <_IO_stdin_used+0xa>
    119b:       e8 d0 fe ff ff          call   1070 <fopen@plt>
    11a0:       48 89 45 e8             mov    QWORD PTR [rbp-0x18],rax
    11a4:       48 8d 35 68 0e 00 00    lea    rsi,[rip+0xe68]        # 2013 <_IO_stdin_used+0x13>
    11ab:       48 8d 3d 63 0e 00 00    lea    rdi,[rip+0xe63]        # 2015 <_IO_stdin_used+0x15>
    11b2:       e8 b9 fe ff ff          call   1070 <fopen@plt>
    11b7:       48 89 45 e0             mov    QWORD PTR [rbp-0x20],rax
    11bb:       48 83 7d e8 00          cmp    QWORD PTR [rbp-0x18],0x0
    11c0:       75 0c                   jne    11ce <main+0x49>
    11c2:       48 8d 3d 57 0e 00 00    lea    rdi,[rip+0xe57]        # 2020 <_IO_stdin_used+0x20>
    11c9:       e8 62 fe ff ff          call   1030 <puts@plt>
    11ce:       48 83 7d e0 00          cmp    QWORD PTR [rbp-0x20],0x0
    11d3:       75 0c                   jne    11e1 <main+0x5c>
    11d5:       48 8d 3d 7e 0e 00 00    lea    rdi,[rip+0xe7e]        # 205a <_IO_stdin_used+0x5a>
    11dc:       e8 4f fe ff ff          call   1030 <puts@plt>
    11e1:       48 8b 55 e8             mov    rdx,QWORD PTR [rbp-0x18]
    11e5:       48 8d 45 b0             lea    rax,[rbp-0x50]
    11e9:       48 89 d1                mov    rcx,rdx
    11ec:       ba 01 00 00 00          mov    edx,0x1
    11f1:       be 18 00 00 00          mov    esi,0x18
    11f6:       48 89 c7                mov    rdi,rax
    11f9:       e8 42 fe ff ff          call   1040 <fread@plt>
    11fe:       89 45 dc                mov    DWORD PTR [rbp-0x24],eax
    1201:       83 7d dc 00             cmp    DWORD PTR [rbp-0x24],0x0
    1205:       7f 0a                   jg     1211 <main+0x8c>
    1207:       bf 00 00 00 00          mov    edi,0x0
    120c:       e8 6f fe ff ff          call   1080 <exit@plt>
    1211:       c7 45 f8 00 00 00 00    mov    DWORD PTR [rbp-0x8],0x0
    1218:       eb 23                   jmp    123d <main+0xb8>
    121a:       8b 45 f8                mov    eax,DWORD PTR [rbp-0x8]
    121d:       48 98                   cdqe
    121f:       0f b6 44 05 b0          movzx  eax,BYTE PTR [rbp+rax*1-0x50]
    1224:       88 45 ff                mov    BYTE PTR [rbp-0x1],al
    1227:       0f be 45 ff             movsx  eax,BYTE PTR [rbp-0x1]
    122b:       48 8b 55 e0             mov    rdx,QWORD PTR [rbp-0x20]
    122f:       48 89 d6                mov    rsi,rdx
    1232:       89 c7                   mov    edi,eax
    1234:       e8 27 fe ff ff          call   1060 <fputc@plt>
    1239:       83 45 f8 01             add    DWORD PTR [rbp-0x8],0x1
    123d:       83 7d f8 07             cmp    DWORD PTR [rbp-0x8],0x7
    1241:       7e d7                   jle    121a <main+0x95>
    1243:       c7 45 f4 08 00 00 00    mov    DWORD PTR [rbp-0xc],0x8
    124a:       eb 43                   jmp    128f <main+0x10a>
    124c:       8b 45 f4                mov    eax,DWORD PTR [rbp-0xc]
    124f:       48 98                   cdqe
    1251:       0f b6 44 05 b0          movzx  eax,BYTE PTR [rbp+rax*1-0x50]
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ python3 exp.py
picoCTF{w1{1wq85jc=2i0<}
r3v3rs37ee84d27
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/reverse_cioher]
└─$ 

```
```
void main(void)

{
  size_t sVar1;
  char local_58 [23];
  char local_41;
  int local_2c;
  FILE *local_28;
  FILE *flagfile;
  uint local_14;
  int local_10;
  char local_9;
  
  flagfile = fopen("flag.txt","r");
  local_28 = fopen("rev_this","a");
  if (flagfile == (FILE *)0x0) {
    puts("No flag found, please make sure this is run on the server");
  }
  if (local_28 == (FILE *)0x0) {
    puts("please run this on the server");
  }
  sVar1 = fread(local_58,0x18,1,flagfile);
  local_2c = (int)sVar1;
  if ((int)sVar1 < 1) {
                    /* WARNING: Subroutine does not return */
    exit(0);
  }
  for (local_10 = 0; local_10 < 8; local_10 = local_10 + 1) {
    local_9 = local_58[local_10];
    fputc((int)local_9,local_28);
  }
  for (local_14 = 8; (int)local_14 < 0x17; local_14 = local_14 + 1) {
    if ((local_14 & 1) == 0) {
      local_9 = local_58[(int)local_14] + '\x05';
    }
    else {
      local_9 = local_58[(int)local_14] + -2;
    }
    fputc((int)local_9,local_28);
  }
  local_9 = local_41;
  fputc((int)local_41,local_28);
  fclose(local_28);
  fclose(flagfile);
  return;
}
```
```python
cifrado = open('rev_this', 'r').read()
print(cifrado)

flag = ''

for i in range( 8, len(cifrado)-1 ):
        if i & 1 == 0:
                flag += chr( ord(cifrado[i]) - 5 )
        else:
                flag += chr( ord(cifrado[i]) + 2 )

print(flag)
```

## Bandera
picoCTF{r3v3rs37ee84d27}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
