## Objetivo.
The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on.

## Datos de Acceso.
ssh bandit13@bandit.labs.overthewire.org -p 2220
bandit13
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Solucion.
``` bash
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit13/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit13/.ssh/known_hosts).

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$

```

## Notas Adicionales.
La contraseña se encuentra almacenada en "/etc/bandit_pass/bandit14" por lo que dentro del servidor del bandit13 ingresamos al bandit14 con el comando "ssh -i sshkey.private bandit14@localhost -p 2220", dentro aplicamos un "cat" a la ruta en donde esta almacenada la contraseña.

## Referencias.

