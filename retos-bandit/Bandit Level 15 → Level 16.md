## Objetivo.
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de Acceso.
ssh bandit15@bandit.labs.overthewire.org -p 2220
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solucion.
``` bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Mar  6 22:20:05 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Mar  6 22:20:05 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Mar  6 22:19:05 2023 GMT; NotAfter: Mar  6 22:20:05 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEPdp+IzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMzA2MjIxOTA1WhcNMjMwMzA2MjIyMDA1WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCg
jgIA2qmltEjw3vzUIAIK1fNai6bUromNC2zbcJgAZn0jVUuSu7vMKMPPDw8TUCqf
o3qbbhF76+KI3LojgYirZ+eY41XWRL5s4QNC7ydPndsF/2PLDoWZY3gkxgePfhvC
FPQEzL6ATIV2xcAewQoh9ifdCm1ffjamFQ+7Sem/V+C7srnwUomZQwzB5GJS8wCz
U1M8YiAjBTrJpJQvWAVdYIBsDFq0MVxYAU5BoyHvKjBFB/CTDXuXFAjKI1wC8qj1
b0gCTcFi0gQNxREFhN9VMhntkOyU/8nXCMSg8EK7rI4WHjRx1XKBiLEKlSs2DKg6
DEakOfmlFUSIwkBAXG7bAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAe
1/W5N0hlOOD6Rd+imZz0Y98aykyjrL6sXxRVFUAGiB06l4fQu6DjONEvdt7XyT8m
7eBdjUe9h+yg6/LrAXznCnViy5o3aDhygTonh8GT/O5EuXqeW9oMMJrad5bXnIWr
GAlQRb8Pzng+WiaF8ZJpvZZfxxFMHadYkt+ElWO30WgO1WFUCRTL9QoTheJGaoPV
qAVBl8kFViX7pKxPLTQVeTK/TSZHWlhwiNQaf/Uoj5HRrnNv7KyajRneEhRW0irk
FjPXWf8/OuvtGUkCykanVu5Jaa/h9HjxnXS/ktK35tArd8ulY2S7eoQnuGK66NNr
Qu4d71t3tUxj5XJS6z46
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
    Session-ID: E8DCABACB6DCF65BB6AA6DFF9201F25964878BF42F9482ACEE9E6F9968A94FE9
    Session-ID-ctx:
    Resumption PSK: 7684772D805EB4C8B08C791B87BC044715E9F66297D9E84FEF048CC3A0E63862F2028EF0EB5732CA446C4DDBE391D8DC
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 0a 44 21 89 48 d6 df a0-94 86 e2 cc a6 54 ac 7c   .D!.H........T.|
    0010 - d4 98 97 38 04 3b 8f 05-7a 21 6e df 40 23 da d1   ...8.;..z!n.@#..
    0020 - 08 45 9e 6d b0 b6 c6 07-d8 1c ba 3d 84 cd 0b 3f   .E.m.......=...?
    0030 - a9 1f 38 76 0a 7d bf 4f-a6 bb 90 36 8b 5d 8e d2   ..8v.}.O...6.]..
    0040 - c1 72 05 3f 79 c9 63 d2-d3 f3 be 48 2b 1b 87 4b   .r.?y.c....H+..K
    0050 - f1 8b ad 2a 54 de dd 98-f6 07 21 24 eb ef f4 78   ...*T.....!$...x
    0060 - d7 28 32 ae 6d 67 b4 df-b0 55 18 0a 54 f6 5a b5   .(2.mg...U..T.Z.
    0070 - 58 f2 28 73 f2 c2 2b 8a-7d e9 b9 36 21 0a aa b1   X.(s..+.}..6!...
    0080 - 88 81 93 de ca f1 7f 2c-20 cc 7c 95 4f 37 a7 ee   ......., .|.O7..
    0090 - 21 b5 a7 a2 f6 cf 2a dc-81 8d 6a 6c 4d 1a 72 99   !.....*...jlM.r.
    00a0 - 3f 6c 20 97 f0 19 e0 07-3b ad 6b 7c a6 30 c8 7b   ?l .....;.k|.0.{
    00b0 - 14 97 11 57 ee c2 49 91-e8 b5 68 99 46 7e 6d 71   ...W..I...h.F~mq
    00c0 - 46 5c 4b 5e 42 a8 54 2f-df 16 91 f5 d5 4f 58 db   F\K^B.T/.....OX.

    Start Time: 1678178107
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
    Session-ID: DBF64D0CC133888ED633DBE50E9F2ED466AA1D4F638CD5FB03C47CCC650543E0
    Session-ID-ctx:
    Resumption PSK: D21845DD9CA40EA26E45B6539EAC06D5B81A08B4DA8521154EAE6C672553DAF862FF17AA791EBECAB541B2D9BA481069
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 0a 44 21 89 48 d6 df a0-94 86 e2 cc a6 54 ac 7c   .D!.H........T.|
    0010 - 2f 39 ca 5d dc 21 19 78-5b c4 90 98 1f 69 a9 09   /9.].!.x[....i..
    0020 - 4e e9 71 12 0b 98 15 6a-c1 5c 34 76 95 19 e8 9e   N.q....j.\4v....
    0030 - 93 64 40 5b 0c c3 67 5e-cd e7 7b a0 82 45 73 09   .d@[..g^..{..Es.
    0040 - b5 ba f8 ad 35 8d fc b2-67 3d e6 c9 2e 81 90 91   ....5...g=......
    0050 - 96 28 b8 56 97 0f f4 77-6c 46 4b 71 fc ff 22 e7   .(.V...wlFKq..".
    0060 - 7d 16 fb 3c 02 68 c7 df-d7 a5 61 33 52 10 1d c7   }..<.h....a3R...
    0070 - a4 8f 4a 9e 7b db 92 ef-b2 ec e3 d8 82 56 f8 52   ..J.{........V.R
    0080 - 37 52 17 e8 1f 46 ff 88-36 6c bb 9a cb e2 c3 f5   7R...F..6l......
    0090 - ce 8d 97 c0 07 5c 2b f0-70 73 8e c2 80 08 f0 37   .....\+.ps.....7
    00a0 - 6f 4d 26 4f da a7 71 23-58 44 89 f9 62 15 fb 90   oM&O..q#XD..b...
    00b0 - a6 74 37 e4 96 5a 77 1f-d8 bb 33 0c de 09 c4 b6   .t7..Zw...3.....
    00c0 - 6c 95 17 df 80 d6 6c ef-c4 d8 56 88 4d 9c 87 6d   l.....l...V.M..m

    Start Time: 1678178107
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$

```

## Notas Adicionales.
El comando openssl s_client -connect localhost:30001 se utiliza para conectarse a un servicio de red seguro que se está ejecutando en el puerto 30001 de la dirección IP de loopback (localhost). Una vez que se establece la conexión SSL/TLS con el servicio de red utilizando el comando "openssl s_client", se puede interactuar con el servicio de red para obtener la contraseña del siguiente nivel se pone la contraseña del bandit15 y nos arroja la contraseña al siguiente nivel.

## Referencias.