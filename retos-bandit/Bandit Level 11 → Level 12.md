## Objetivo.
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

## Datos de Acceso.
ssh bandit11@bandit.labs.overthewire.org -p 2220
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solucion.
``` bash
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ python3
Python 3.10.6 (main, Nov 14 2022, 16:10:14) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> codecs.decode('Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi','rot13'
)
'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'
>>>

```
## Notas Adicionales.
Para llegar a la contraseña primero aplicamos un "cat" al archivo "data.txt" lo que nos muestra una codificacion de la contraseña que no podemos entender, usamos el comando "python3" lo que hace que usemos una terminal python para usar la herramienta de decodificacion de python, importamos los codecs usando "import codecs", despues usamos codecs.decode('Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi','rot13'), dentro del comando pusimos la linea de codigo codificada de la contraseña y nos la muestra al instante.

## Referencias.