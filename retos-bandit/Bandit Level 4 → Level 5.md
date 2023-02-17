## Objetivo.
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos de Acceso.
ssh bandit4@bandit.labs.overthewire.org -p 2220
bandit4
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Solucion.
``` bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls -la
total 48
drwxr-xr-x 2 root    root    4096 Jan 11 19:19 .
drwxr-xr-x 3 root    root    4096 Jan 11 19:19 ..
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file00
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file01
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file02
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file03
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file04
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file05
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file06
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file07
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file08
-rw-r----- 1 bandit5 bandit4   33 Jan 11 19:19 -file09
bandit4@bandit:~/inhere$ cat ./-file00
T߼��B�������#6�Kt�3�
                     �6X��t���)bandit4@bandit:~/inhere$ file ./-file00
./-file00: data
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$

```

## Notas Adicionales.
Para encontrar la contraseña tuvimos que dirigirnos a la carpeta inhere y hacer un cat al ./file00 para saber su contenido, una vez ahi aplicamos un file ./file00 para identificar el tipo de archivo que es ./file00, una vez hecho eso aplicamos otro file a ./*  para que me mostrara todos los archivos que se encontraban ahi y el fromato de los mismos, el objetivo del nivel es encontrar la contraseña en un formato legible para humanos considerando que "data" es codigo binario el codigo ASCII es el unico legible para humanos por lo que le hacemos un cat al ./file07 para que nos muestre el contenido (ya que es el archvio con formato ASCIII legible) y asi nos muestra la contraseña del siguiente nivel.

## Referencias.