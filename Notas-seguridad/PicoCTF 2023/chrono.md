## Descripción
How to automate tasks to run at intervals on linux servers?

## Solución


```bash

picoplayer@challenge:~$ find / -name '*.json' -exec grep -i 'pico*' {} \; -print
find: ‘/etc/ssl/private’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
find: ‘/proc/8/task/8/fd’: Permission denied
find: ‘/proc/8/task/8/fdinfo’: Permission denied
find: ‘/proc/8/task/8/ns’: Permission denied
find: ‘/proc/8/fd’: Permission denied
find: ‘/proc/8/map_files’: Permission denied
find: ‘/proc/8/fdinfo’: Permission denied
find: ‘/proc/8/ns’: Permission denied
find: ‘/proc/41/task/41/fd’: Permission denied
find: ‘/proc/41/task/41/fdinfo’: Permission denied
find: ‘/proc/41/task/41/ns’: Permission denied
find: ‘/proc/41/fd’: Permission denied
find: ‘/proc/41/map_files’: Permission denied
find: ‘/proc/41/fdinfo’: Permission denied
find: ‘/proc/41/ns’: Permission denied
find: ‘/proc/52/task/52/fd’: Permission denied
find: ‘/proc/52/task/52/fdinfo’: Permission denied
find: ‘/proc/52/task/52/ns’: Permission denied
find: ‘/proc/52/fd’: Permission denied
find: ‘/proc/52/map_files’: Permission denied
find: ‘/proc/52/fdinfo’: Permission denied
find: ‘/proc/52/ns’: Permission denied
find: ‘/root’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/spool/cron/crontabs’: Permission denied
{"flag": "picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}", "username": "picoplayer", "password": "KkPyI5bkmn"}
/challenge/metadata.json

```

## Notas Adicionales
|comando|descripcion|
|---|---|
|xx|xx|

## Referencias
- []()
