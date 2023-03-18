## Objetivo.
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de Acceso.
ssh bandit16@bandit.labs.overthewire.org -p 2220
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solucion.
```bash
bandit16@bandit:~$ nmap -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-03-14 03:29 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00017s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.05 seconds
bandit16@bandit:~$ echo "JQttfApK4SeyHwDlI9SXGR50qclOAil1" | openssl s_client -connect localhost:31790 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Mar 13 23:39:41 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Mar 13 23:39:41 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Mar 13 23:38:41 2023 GMT; NotAfter: Mar 13 23:39:41 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEcfsMPDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMzEzMjMzODQxWhcNMjMwMzEzMjMzOTQxWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCr
tfHLWIz1ZnFk1cp8VOchde+ydIfoVxoj9wHVwRzHjlQoxhf9hn1txHCJ73jUm1cm
dYYumr9j2XyH/lpv9lDHTgeU1bblgMbko6eEfT6kZM8CYTqep4q3sOcZyAIozObf
wBLKVSCO9tAB3kMHcDvyr3izkGkz6khlQUAFUHAeKZSbz5KUrml33BTjyubY+iz1
eb9Y9mgaQKDUQXB5+5Iu3UrMy0mafvCKuah6P81yocSfghUbcylTMgP5OyvkwTip
/P5O8+2hEBPTM+WiHav/agwK1cJdQnsZAJTwAvoikPJGpozibVeOWzKm881U+41o
TA+kZY7+fJ1cWk49WqBRAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAH
IyfjmBl9oGAUXT96OAXXujOGgBnH7ADPzxtTljKjp+zNtbiQPt51EKhFGdfDSw/Y
+64HKMExGFD6Cc5y6fuoWn76kSkyIKwbGhIX/g8gleoDMfmY72YNpvuhQRUtlmvz
7HHtMT0UZ47gzOwj31kR1KCaYY28sCeJE24UAc5HxMy3gF/g9S0Ev4ky+0Hoy1Z/
q2LlFUTmiqR+dAwC7n0ycUDsga2Z+MdV1X4k2ZB5WSr7S0NYEYV8KVr2CPyEWovZ
o5eD6wnvjOv9tozG4IZFvooxE+gqQ/ygdj6iiF4cACweNJllD4pPABXcbIpi1Amh
iT0Jdz739K5xTELkOHtJ
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 851ED773244073013015691F0B57CAFC423CCE6B3FBB6ECFF82B6BBA4A7ABDDD
    Session-ID-ctx: 
    Resumption PSK: 7E332A9D49342A59B704909F9B5D88B89048331FBCCAF172DCFACFAF71CF508189400D0AEC7AC664276D38F23BF61946
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 51 16 b8 ba 3d f4 ec 43-08 9a 8b 49 28 cc 66 c9   Q...=..C...I(.f.
    0010 - d1 c5 65 ef 76 f1 36 f8-2e 16 df c5 bd e8 f1 e2   ..e.v.6.........
    0020 - 3b 75 60 e4 6a f4 86 16-8d e0 93 9f 19 3c f0 bd   ;u`.j........<..
    0030 - 1f 1a 6f df ca 88 11 80-30 59 e7 08 8a a6 df 7d   ..o.....0Y.....}
    0040 - b3 9a 47 6d 7d a4 ee 35-98 8b 8d 66 2d 2e 81 8e   ..Gm}..5...f-...
    0050 - a4 50 7d 87 79 10 4a 59-18 3a 2f 86 9d 1b a5 0c   .P}.y.JY.:/.....
    0060 - d5 15 99 ae 02 27 83 c1-ca 75 6d 9e f5 ae 44 62   .....'...um...Db
    0070 - 60 1e 2d 6e a3 56 8b 80-3c a4 6f ba 57 9b 8e db   `.-n.V..<.o.W...
    0080 - 70 2f 2f 63 f6 cb b6 63-24 78 0c e2 74 e5 8e 3c   p//c...c$x..t..<
    0090 - 8c 03 e3 fe 62 97 22 d3-f9 90 58 7b 4c 3e d7 f5   ....b."...X{L>..
    00a0 - b3 61 d2 ee 4f a8 0e f3-36 bf ff 87 0c b1 dc a3   .a..O...6.......
    00b0 - 3d d7 c3 83 12 5d f7 de-85 e7 0d e6 a1 42 93 4c   =....].......B.L
    00c0 - 9d 57 fe 5f fc bc a7 a5-3c fb 5f c9 2b 18 09 97   .W._....<._.+...

    Start Time: 1678764652
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: BADB182905AA96755617E0565520B252322B6B0B9147171852D07E0B05927D1F
    Session-ID-ctx: 
    Resumption PSK: 973762E300FFF38985A5BF697E0D556EF550607927C5EF448F16543A2F77EAC233B412262F5365BE47D52520201B55F5
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 51 16 b8 ba 3d f4 ec 43-08 9a 8b 49 28 cc 66 c9   Q...=..C...I(.f.
    0010 - b6 3d d6 c9 8c ed 8a 7a-1a 4e ee ae 74 b3 e6 c8   .=.....z.N..t...
    0020 - 2e fb 9e ee d9 9c 62 60-76 2a 00 aa 60 87 33 5e   ......b`v*..`.3^
    0030 - f6 5e 12 2c d1 72 84 56-44 e1 97 67 70 2d be 09   .^.,.r.VD..gp-..
    0040 - 03 ef 12 30 68 64 bc b0-d3 6c 13 f5 ef af 63 2c   ...0hd...l....c,
    0050 - ef 9d 85 b4 10 ba fe f2-cf 8e 87 a8 d5 4d b6 df   .............M..
    0060 - 2b d2 0f 92 ac d1 28 56-b9 99 d1 92 aa 47 62 2a   +.....(V.....Gb*
    0070 - b1 e5 70 5f ea 87 b6 b7-4f 80 0e 8a 15 7c 3e ce   ..p_....O....|>.
    0080 - 9e 5e 11 ff 8b e9 87 a5-17 5e ae 3a 66 7d 25 ed   .^.......^.:f}%.
    0090 - f1 18 3b b9 02 28 a2 7b-64 0b 36 7b e7 c2 b5 db   ..;..(.{d.6{....
    00a0 - 9d 03 68 40 73 c5 ff d5-7c 03 9d 0d 07 ac ca f1   ..h@s...|.......
    00b0 - d7 c5 62 86 44 da 7a 98-b4 1e 30 e0 ce 99 9f 4c   ..b.D.z...0....L
    00c0 - 7d bb 9b d1 ab 8d b9 53-92 d3 f3 1d 99 36 cf 6f   }......S.....6.o

    Start Time: 1678764652
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed

C:\Users\jesus>notepad llave.txt

C:\Users\jesus>type llave.txt

C:\Users\jesus>type llave.txt
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----
C:\Users\jesus>ssh -i llave.txt
usage: ssh [-46AaCfGgKkMNnqsTtVvXxYy] [-B bind_interface]
           [-b bind_address] [-c cipher_spec] [-D [bind_address:]port]
           [-E log_file] [-e escape_char] [-F configfile] [-I pkcs11]
           [-i identity_file] [-J [user@]host[:port]] [-L address]
           [-l login_name] [-m mac_spec] [-O ctl_cmd] [-o option] [-p port]
           [-Q query_option] [-R address] [-S ctl_path] [-W host:port]
           [-w local_tun[:remote_tun]] destination [command]

C:\Users\jesus>ssh -i llave.txt bandit17@bandit.labs.overthewire.org -p2220
bandit17@bandit:~$ ls
passwords.new  passwords.old
bandit17@bandit:~$ cat /etc/bandit_pass/bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
bandit17@bandit:~$

```

## Notas Adicionales.
Una vez conectado, ejecuta el siguiente comando para encontrar los puertos en localhost que tienen un servidor escuchando "nmap -sT -p31000-32000 localhost", este comando utilizará la herramienta Nmap para realizar un escaneo de puertos en localhost en el rango de puertos de 31000 a 32000 y mostrará los puertos que tienen un servidor escuchando.
Analizamos los resultados y enviamos la contraseña del nivel anterior con el siguiente comando "echo "JQttfApK4SeyHwDlI9SXGR50qclOAil1" | openssl s_client -connect localhost:31790 -ign_eof" una vez hecho esto, desde afuera de la terminal linux vamos a crear un archivo llamad "llave.txt" en donde vamos a almacenar la llave privada que nos dieron anteriormente, guardamos y usamos el siguiente comando el terminal para conectarnos al nivel 17 "ssh -i llave.txt bandit17@bandit.labs.overthewire.org -p2220", dentro podemos usar el comando "cat /etc/bandit_pass/bandit17" para saber la contraseña del nivel.

## Referencias.