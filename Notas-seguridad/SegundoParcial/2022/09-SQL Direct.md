# SQL Direct
#picoCTF 
## Descripción
Connect to this PostgreSQL server and find the flag! `psql -h saturn.picoctf.net -p 65125 -U postgres pico` Password is `postgres`

## Pistas 

## Solución
Te conectas al servidor con los datos que te arroja la instancia, despues listas las bases de adtos y puedes ver una que se llama "pico", la seleccionas y muetras las tablas que tiene, y se puede ver que tiene una tabla llamada flags, y listando su contenido encuentras la bandera.
```bash 
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 65125 -U postgres pico
Password for user postgres: 
psql (15.2 (Debian 15.2-2))
Type "help" for help.

pico=# \l
                                                List of databases
   Name    |  Owner   | Encoding |  Collate   |   Ctype    | ICU Locale | Locale Provider |   Access privileges   
-----------+----------+----------+------------+------------+------------+-----------------+-----------------------
 pico      | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | 
 postgres  | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | 
 template0 | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | =c/postgres          +
           |          |          |            |            |            |                 | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | =c/postgres          +
           |          |          |            |            |            |                 | postgres=CTc/postgres
(4 rows)

pico=# \c pico
You are now connected to database "pico" as user "postgres".
pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 

```
## Bandera
picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

## Notas adicionales
| comando | descripción |
|------------|---------------|
| \\l | muestra las bases de datos |
| \\c [db]| Selecciona la base de datos |
| \\dt | muestra las tablas de la base de datos seleccionada |
## Referencias
