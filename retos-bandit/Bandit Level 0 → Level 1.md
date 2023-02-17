## Objetivo.
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Datos de Acceso.
bandit0
bandit0

## Solucion.
``` bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$

ssh bandit1@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit1@bandit.labs.overthewire.org's password:

bandit1@bandit:~$
```

## Notas Adicionales.
Primero ingresamos al nivel 0 en donde se encontraba un archivo "readme" en donde se encontraba la contraseña para loguearnos en el nivel 0 a 1 de bandit, una vez que encontramos la contraseña cerramos la sesion del nivel 0 e iniciamos una nueva del nivel 0 a 1 ya no con bandit0 sino con bandit1 como host.

## Referencias.
