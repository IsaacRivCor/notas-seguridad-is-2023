# Bandit Level 27 → Level 28
#bandit 
## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Datos de acceso
bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solución
```bash
bandit27@bandit:~$ mktemp -d
/tmp/tmp.5Zk6rnBqYz
bandit27@bandit:~$ cd /tmp/tmp.5Zk6rnBqYz
bandit27@bandit:/tmp/tmp.5Zk6rnBqYz$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/tmp.5Zk6rnBqYz$ ls -la
total 120
drwx------    3 bandit27 bandit27   4096 Feb 28 19:27 .
drwxrwx-wt 3077 root     root     110592 Feb 28 19:28 ..
drwxrwxr-x    3 bandit27 bandit27   4096 Feb 28 19:27 repo
bandit27@bandit:/tmp/tmp.5Zk6rnBqYz$ cd repo/
bandit27@bandit:/tmp/tmp.5Zk6rnBqYz/repo$ ls -la
total 16
drwxrwxr-x 3 bandit27 bandit27 4096 Feb 28 19:27 .
drwx------ 3 bandit27 bandit27 4096 Feb 28 19:27 ..
drwxrwxr-x 8 bandit27 bandit27 4096 Feb 28 19:27 .git
-rw-rw-r-- 1 bandit27 bandit27   68 Feb 28 19:27 README
bandit27@bandit:/tmp/tmp.5Zk6rnBqYz/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/tmp.5Zk6rnBqYz/repo$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|xx|xx|

## Referencias
