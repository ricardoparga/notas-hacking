## Objetivo.
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de Acceso.
ssh bandit9@bandit.labs.overthewire.org -p 2220
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solucion.
``` bash
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep =====
f========== theM
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$

```

## Notas Adicionales.
Utilizamos el comando "strings" para el archivo "data.txt" para que nos muestre las cadenas de caracteres que no sepamos que son de texto plano, es decir un archivo de texto simple, separamos con la barra larga uy en seguida el comando "grep" y como palabra clave usamos los signos de igual "=" ya que una de las condiciones para encontrar la contraseña es que le preceden muchos signos de igualdad.

## Referencias.