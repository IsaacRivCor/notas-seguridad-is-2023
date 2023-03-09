# Static ain't always noise
#picoCTF 
## Descripción
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static)? This [BASH script](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh) might help!

## Pistas 

## Solución
```shell 
isaacrivcor-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static
--2023-03-09 03:31:51--  https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                          100%[======================================================>]   8.18K  --.-KB/s    in 0s      

2023-03-09 03:31:51 (220 MB/s) - 'static' saved [8376/8376]

isaacrivcor-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh
--2023-03-09 03:32:03--  https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                        100%[======================================================>]     785  --.-KB/s    in 0s      

2023-03-09 03:32:03 (303 MB/s) - 'ltdis.sh' saved [785/785]

isaacrivcor-picoctf@webshell:~$ ls
README.txt  file  flag  ltdis.sh  static  strings  warm
isaacrivcor-picoctf@webshell:~$ ls -la
total 844
drwxr-xr-x 3 isaacrivcor-picoctf isaacrivcor-picoctf   4096 Mar  9 03:32 .
drwxr-xr-x 3 root                root                    33 Mar  2 18:36 ..
-rw------- 1 isaacrivcor-picoctf isaacrivcor-picoctf    484 Mar  9 02:54 .bash_history
-rw-r--r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf    220 Mar  2 18:36 .bash_logout
-rw-r--r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf   3771 Mar  2 18:36 .bashrc
drwxrwxr-x 3 isaacrivcor-picoctf isaacrivcor-picoctf     19 Mar  9 03:26 .local
-rw-r--r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf    807 Mar  2 18:36 .profile
-rw------- 1 isaacrivcor-picoctf isaacrivcor-picoctf    375 Mar  9 03:28 .python_history
-rw-rw-r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf    178 Mar  9 03:32 .wget-hsts
-rw-r--r-- 1 root                root                  4443 Mar  9 03:17 README.txt
-rw-rw-r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf  14551 Oct 26  2020 file
-rw-rw-r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf     34 Mar 16  2021 flag
-rw-rw-r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf    785 Mar 16  2021 ltdis.sh
-rw-rw-r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf   8376 Mar 16  2021 static
-rw-rw-r-- 1 isaacrivcor-picoctf isaacrivcor-picoctf 776032 Oct 26  2020 strings
-rwxrwxr-x 1 isaacrivcor-picoctf isaacrivcor-picoctf  10936 Mar 16  2021 warm
isaacrivcor-picoctf@webshell:~$ file static 
static: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=7eb9ee1907cc878f15f9949988893b1f0ab1ebdf, not stripped
isaacrivcor-picoctf@webshell:~$ nano ltdis.sh 
isaacrivcor-picoctf@webshell:~$ ltdis.sh 
-bash: ltdis.sh: command not found
isaacrivcor-picoctf@webshell:~$ ./ltdis
-bash: ./ltdis: No such file or directory
isaacrivcor-picoctf@webshell:~$ ./ltdis static 
-bash: ./ltdis: No such file or directory
isaacrivcor-picoctf@webshell:~$ chmod 775 ltdis.sh
isaacrivcor-picoctf@webshell:~$ ./ltdis static 
-bash: ./ltdis: No such file or directory
isaacrivcor-picoctf@webshell:~$ ./ltdis.sh static 
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
isaacrivcor-picoctf@webshell:~$ ls
README.txt  file  flag  ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt  strings  warm
isaacrivcor-picoctf@webshell:~$ sta
start-stop-daemon  stat               
isaacrivcor-picoctf@webshell:~$ file static.ltdis.strings.txt
static.ltdis.strings.txt: ASCII text
isaacrivcor-picoctf@webshell:~$ cat static.ltdis.strings.txt
    238 /lib64/ld-linux-x86-64.so.2
    361 libc.so.6
    36b puts
    370 __cxa_finalize
    37f __libc_start_main
    391 GLIBC_2.2.5
    39d _ITM_deregisterTMCloneTable
    3b9 __gmon_start__
    3c8 _ITM_registerTMCloneTable
    660 AWAVI
    667 AUATL
    6ba []A\A]A^A_
    6e8 Oh hai! Wait what? A flag? Yes, it's around here somewhere!
    7c7 ;*3$"
   1020 picoCTF{d15a5m_t34s3r_ae0b3ef2}
   1040 GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0
   1671 crtstuff.c
   167c deregister_tm_clones
   1691 __do_global_dtors_aux
   16a7 completed.7698
   16b6 __do_global_dtors_aux_fini_array_entry
   16dd frame_dummy
   16e9 __frame_dummy_init_array_entry
   1708 static.c
   1711 __FRAME_END__
   171f __init_array_end
   1730 _DYNAMIC
   1739 __init_array_start
   174c __GNU_EH_FRAME_HDR
   175f _GLOBAL_OFFSET_TABLE_
   1775 __libc_csu_fini
   1785 _ITM_deregisterTMCloneTable
   17a1 puts@@GLIBC_2.2.5
   17b3 _edata
   17ba __libc_start_main@@GLIBC_2.2.5
   17d9 __data_start
   17e6 __gmon_start__
   17f5 __dso_handle
   1802 _IO_stdin_used
   1811 __libc_csu_init
   1821 __bss_start
   182d main
   1832 __TMC_END__
   183e _ITM_registerTMCloneTable
   1858 flag
   185d __cxa_finalize@@GLIBC_2.2.5
   187a .symtab
   1882 .strtab
   188a .shstrtab
   1894 .interp
   189c .note.ABI-tag
   18aa .note.gnu.build-id
   18bd .gnu.hash
   18c7 .dynsym
   18cf .dynstr
   18d7 .gnu.version
   18e4 .gnu.version_r
   18f3 .rela.dyn
   18fd .rela.plt
   1907 .init
   190d .plt.got
   1916 .text
   191c .fini
   1922 .rodata
   192a .eh_frame_hdr
   1938 .eh_frame
   1942 .init_array
   194e .fini_array
   195a .dynamic
   1963 .data
   1969 .bss
   196e .comment
isaacrivcor-picoctf@webshell:~$ grep 'pico' static.ltdis.strings.txt       
   1020 picoCTF{d15a5m_t34s3r_ae0b3ef2}
isaacrivcor-picoctf@webshell:~$ 
```
## Bandera
picoCTF{}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
