## Objetivo.
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.

## Datos de Acceso.
ssh bandit8@bandit.labs.overthewire.org -p 2220
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Solucion.
``` bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$

```

## Notas Adicionales.
Para encontrar la contraseña usamos un "cat" al archivo "data.txt" seguida una barra larga "|" usando el comando "sort" para ordenar las lineas de texto del archivo, otra barra larga y seguido el comando "uniq" que originalmente nos sirve para mostrarnos las palabras que se repiten pero buscamos la unica palabra que no se repite, para esto enseguida del comando pondremos "-u" y de esta manera nos muestra la palabra unica en el archivo.

## Referencias.