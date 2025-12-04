# Índex

- Instal·lació del servidor SSH

- Verificació de la connexió SSH

- Configuració del servidor SSH

- Gestió d'usuaris i permisos

- Creació de túnels SSH i ús de proxy SOCKS

## Instal·lació del servidor SSH

Per instal·lar el servei SSH a Ubuntu Server, executa:

![captura1](img/5.png)


sudo apt install ssh

Després, verifica l'adreça IP del servidor amb:

ip addr show



Verificació de la connexió SSH

Des del client Windows, obre PowerShell i connecta't al servidor amb:

ssh usuari@192.168.1.38

La primera vegada, se't demanarà confirmar l'autenticitat del host:



Un cop connectat, veuràs el missatge de benvinguda del sistema Ubuntu:



Configuració del servidor SSH

El fitxer de configuració es troba a:

/etc/ssh/sshd_config

Algunes opcions importants:

PermitRootLogin prohibit-password
StrictModes yes
RSAAuthentication yes
PubkeyAuthentication yes
AuthorizedKeysFile %h/.ssh/authorized_keys



Per aplicar els canvis:

sudo systemctl restart ssh

Gestió d'usuaris i permisos

Pots crear un nou usuari amb:

sudo adduser usuari2



Per restringir l'accés SSH només a certs usuaris, afegeix al sshd_config:

AllowUsers usuari

Verifica que l'usuari restringit no pugui accedir:



Creació de túnels SSH i ús de proxy SOCKS

Pots crear un túnel SSH amb:

ssh -D 9876 usuari@192.168.56.106



Després, configura el navegador per utilitzar un proxy SOCKS a 127.0.0.1:9876:



Verifica amb Wireshark que el trànsit es redirigeix pel túnel SSH:



Aquesta guia cobreix des de la instal·lació bàsica fins a l'ús avançat de SSH com a túnel segur. Pots ampliar cada secció segons les teves necessitats o entorn de xarx
