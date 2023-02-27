## Objetivo.
The password for the next level is stored **somewhere on the server** and has all of the following properties:

-   owned by user bandit7
-   owned by group bandit6
-   33 bytes in size

## Datos de Acceso.
ssh bandit6@bandit.labs.overthewire.org -p 2220
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Solucion.
``` bash
bandit6@bandit:~$ ls
bandit6@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Feb 21 22:02 .
drwxr-xr-x 70 root root 4096 Feb 21 22:04 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$

```

## Notas Adicionales.
Para saber la contraseña del siguiente nivel tuvimos que hacer un la al nivel en el que estabamos pero percatandonos de que no nos muestra nada por lo que hacemos un ls -la para que nos muestre los archivos ocultos, para encontrar la contraseña sabemos que la tiene el usuario bandit 7 en el grupo e bandit 6 y que tiene un tamaño de 33 bytes por lo que usamos el comando "find" con esas especificacines -> "find / -user bandit7 -group bandit6 -size 33c 2>/dev/null" a lo que nos muestra la siguiente ruta con los datos especificados -> "/var/lib/dpkg/info/bandit7.password", copiamos la ruta sobre el comando "cat" para que nos muestre el texto dentro del archivo "bandit7.password".

## Referencias.