## Objetivo.
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

-   human-readable
-   1033 bytes in size
-   not executable

## Datos de Acceso.
ssh bandit5@bandit.labs.overthewire.org -p 2220
bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Solucion.
``` bash
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls -la
total 88
drwxr-x--- 22 root bandit5 4096 Feb 21 22:03 .
drwxr-xr-x  3 root root    4096 Feb 21 22:03 ..
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere00
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere01
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere02
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere03
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere04
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere05
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere06
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere07
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere08
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere09
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere10
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere11
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere12
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere13
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere14
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere15
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere16
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere17
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere18
drwxr-x---  2 root bandit5 4096 Feb 21 22:03 maybehere19
bandit5@bandit:~/inhere$ find . -readable -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
            bandit5@bandit:~/inhere$

```

## Notas Adicionales.
Para encontrar la contraseña al siguiente nivel tuvimos que poner un comando ls para saber lo que contenia el nivel, nos mostro el directorio "inhere", dentro del directorio ejecutamos un ls -la para saber el contenido del directorio, una vez dentro debemos buscar un archivo que sea human-readable, no ejecutable y de 1033 bytes de tamaño para lo que usamos el comando "find . -readable -type f -size 1033c" una vez ejecutado nos muestra el archuvo "./maybehere07/.file2" mismo al que le hacemos un "cat" para saber su contenido y que nos muestre la contraseña al siguiente nivel.

## Referencias.
