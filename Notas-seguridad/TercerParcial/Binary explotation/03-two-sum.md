# two-sum
#picoCTF 
## Descripción
Can you solve this? What two positive numbers can make this possible: `n1 > n1 + n2 OR n2 > n1 + n2` Enter them here `nc saturn.picoctf.net 52989`. [Source](https://artifacts.picoctf.net/c/454/flag.c)

## Pistas 
+ Integer overflow
+ Not necessarily a math problem

## Solución
```bash 
┌──(kali㉿kali)-[~/TercerParcial/Binary/two-sum]
└─$ wget https://artifacts.picoctf.net/c/454/flag.c                                                 
--2023-05-24 21:27:53--  https://artifacts.picoctf.net/c/454/flag.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.56, 13.249.74.17, 13.249.74.69, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.56|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1346 (1.3K) [application/octet-stream]
Saving to: ‘flag.c’

flag.c                       100%[==============================================>]   1.31K  --.-KB/s    in 0s      

2023-05-24 21:27:53 (43.3 MB/s) - ‘flag.c’ saved [1346/1346]

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Binary/two-sum]
└─$ ls
flag.c
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Binary/two-sum]
└─$ cat flag.c  
#include <stdio.h>
#include <stdlib.h>

static int addIntOvf(int result, int a, int b) {
    result = a + b;
    if(a > 0 && b > 0 && result < 0)
        return -1;
    if(a < 0 && b < 0 && result > 0)
        return -1;
    return 0;
}

int main() {
    int num1, num2, sum;
    FILE *flag;
    char c;

    printf("n1 > n1 + n2 OR n2 > n1 + n2 \n");
    fflush(stdout);
    printf("What two positive numbers can make this possible: \n");
    fflush(stdout);
    
    if (scanf("%d", &num1) && scanf("%d", &num2)) {
        printf("You entered %d and %d\n", num1, num2);
        fflush(stdout);
        sum = num1 + num2;
        if (addIntOvf(sum, num1, num2) == 0) {
            printf("No overflow\n");
            fflush(stdout);
            exit(0);
        } else if (addIntOvf(sum, num1, num2) == -1) {
            printf("You have an integer overflow\n");
            fflush(stdout);
        }

        if (num1 > 0 || num2 > 0) {
            flag = fopen("flag.txt","r");
            if(flag == NULL){
                printf("flag not found: please run this on the server\n");
                fflush(stdout);
                exit(0);
            }
            char buf[60];
            fgets(buf, 59, flag);
            printf("YOUR FLAG IS: %s\n", buf);
            fflush(stdout);
            exit(0);
        }
    }
    return 0;
}
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Binary/two-sum]
└─$ nc saturn.picoctf.net 52989
n1 > n1 + n2 OR n2 > n1 + n2 
What two positive numbers can make this possible: 
6
3
You entered 6 and 3
No overflow
                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Binary/two-sum]
└─$ nc saturn.picoctf.net 52989
n1 > n1 + n2 OR n2 > n1 + n2 
What two positive numbers can make this possible: 
2147483647
1
You entered 2147483647 and 1
You have an integer overflow
YOUR FLAG IS: picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_f6ed8057}

                                                                                                                    
┌──(kali㉿kali)-[~/TercerParcial/Binary/two-sum]
└─$ 
```

## Bandera
picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_f6ed8057}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
