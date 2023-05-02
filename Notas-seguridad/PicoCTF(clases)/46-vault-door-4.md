# vault-door-4
#picoCTF 
## Descripción
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java)

## Pistas 
+ Use a search engine to find an "ASCII table".
+ You will also need to know the difference between octal, decimal, and hexadecimal numbers.

## Solución
``` bash
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ wget https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java
--2023-05-02 19:08:07--  https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1497 (1.5K) [application/octet-stream]
Saving to: ‘VaultDoor4.java’

VaultDoor4.java              100%[==============================================>]   1.46K  --.-KB/s    in 0s      

2023-05-02 19:08:07 (56.8 MB/s) - ‘VaultDoor4.java’ saved [1497/1497]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ ls
VaultDoor4.java
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ cat VaultDoor4.java 
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 0143, 061 ,
            '9' , '4' , 'f' , '7' , '4' , '5' , '8' , 'e' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ nano VaultDoor4.java 
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ javac VaultDoor4.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
VaultDoor4.java:46: error: ';' expected
        System.out.println(flag)
                                ^
1 error
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ nano VaultDoor4.java 
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ javac VaultDoor4.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ java VaultDoor4      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
jU5t_4_bUnCh_0f_bYt3s_c194f7458e
Access granted.
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]
└─$ 
```

## Bandera
picoCTF{jU5t_4_bUnCh_0f_bYt3s_c194f7458e}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| xx | xx |

## Referencias
