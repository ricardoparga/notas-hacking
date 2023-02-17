## Objetivo.
The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso.
ssh bandit1@bandit.labs.overthewire.org -p 2220
bandit1
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

## Solucion.
``` bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$

```

## Notas Adicionales.
Para encontrar la contraseña del siguiente nivel hicimos un ls para saber que archivos se encontraban, hicimos un cat para saber su contenido y asi nos arrojo la contraseña del siguiente nivel, al igual que usamos un pwd para ver la ruta del directorio actual, le hicimos un cat a la ruta y nos mostro la misma contraseña, son dos formas diferentes de poder llegar al archivo.

## Referencias.