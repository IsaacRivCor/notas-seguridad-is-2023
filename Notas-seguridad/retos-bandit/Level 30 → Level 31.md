# Level X
#bandit 
## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de acceso
bandit30 
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solución
```shell
bandit30@bandit:~$ mktemp -d
/tmp/tmp.AaYR5uP8Uh
bandit30@bandit:~$ cd /tmp/tmp.AaYR5uP8Uh
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), 299 bytes | 299.00 KiB/s, done.
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh$ ls
repo
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh$ cd repo/
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo$ ls
README.md
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo$ git log
commit cf552c166d78421e64ddf52f850e680075d216e1 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:13 2023 +0000

    initial commit of README.md
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo$ git reflog
cf552c1 (HEAD -> master, origin/master, origin/HEAD) HEAD@{0}: clone: from ssh://localhost:2220/home/bandit30-git/repo
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo$ cd .git
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo/.git$ ls
branches  config  description  HEAD  hooks  index  info  logs  objects  packed-refs  refs
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo/.git$ cat packed-refs
# pack-refs with: peeled fully-peeled sorted
cf552c166d78421e64ddf52f850e680075d216e1 refs/remotes/origin/master
831aac2e2341f009e40e46392a4f5dd318483019 refs/tags/secret
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo/.git$ git show 831aac2e2341f009e40e46392a4f5dd318483019
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/tmp.AaYR5uP8Uh/repo/.git$
```
## Notas adicionales
| comando | descripción |
|----------|----------|
|git reflog|muestra el registro de referencias de los commits |

## Referencias
