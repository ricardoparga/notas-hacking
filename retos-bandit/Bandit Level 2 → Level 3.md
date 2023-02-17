## Objetivo.
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Datos de Acceso.
ssh bandit2@bandit.labs.overthewire.org -p 2220
bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Solucion.
``` bash
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$

```

## Notas Adicionales.
Sacamos la contraseña del siguiente nivel haciendo un ls para identificar el archivo en donde se encontraba la contraseña, como el directorio tenia espacios en el nombre el cat que usamos para ingresar fue con diagonales invertidas.

## Referencias.