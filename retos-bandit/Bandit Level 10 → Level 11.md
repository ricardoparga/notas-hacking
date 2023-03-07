## Objetivo.
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Datos de Acceso.
ssh bandit10@bandit.labs.overthewire.org -p 2220
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solucion.
``` bash
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$

```

## Notas Adicionales.
Para encontrar la contraseña nos indica Bandit que contiene un "base64" de codificacion que es codificación de binario a texto que representa los datos binarios mediante una cadena ASCII, hacemos un "cat" al archivo, separamos con barra larga y ponemos la codificacion (base64) seguido de un -d para que nos muestre la contraseña.

## Referencias.