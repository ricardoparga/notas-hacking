## Objetivo.
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos de Acceso.
ssh bandit7@bandit.labs.overthewire.org -p 2220
bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solucion.
``` bash
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ wc data.txt
  98567  197133 4184396 data.txt
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$

```

## Notas Adicionales.
Para encontrar la contraseña neceitamos del comando ls para que nos muestre lo que se encuentra dentro del servidor de bandit7, nos muestra el archivo "data.txt" donde si hacemos un cat nos muestra un listado gigante de palabras junto a varias contraseñas, para bucar la palabra clave de nuestra contraseña al siguiente servidor que es "millionth" debemos hacer un "cat" a "data.txt" seguido de una barra larga "|" y seguida del comando "grep" que basicamente nos imprime toda la linea de texto en donde venga nuestra palabra clave.

## Referencias.