## Objetivo.
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de Acceso.
ssh bandit14@bandit.labs.overthewire.org -p 2220
bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solucion.
``` bash
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

^C
bandit14@bandit:~$

```

## Notas Adicionales.
Nos conectamos al servicio de red usando "nc o netcat" seguida de la direccion ip "localhost" y el numero de puerto 30,000 para establecer la conexion, una vez hecho ingresamos la contraseña del nivel y nos lanza la del siguiente reto.

## Referencias.
