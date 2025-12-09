# Servidor NFS

Cal desplegar dues màquines virtuals, una amb el rol de Client i una altra amb el rol de Servidor. Cada VM haurà de disposar de dos interfícies de xarxa: una configurada en mode NAT i una altra configurada en mode host-only.
S'haurà de actualitzar el sistema operatiu a les dues màquines.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

```bash
sudo apt update -y && sudo apt upgrade -y
```
![Capt1](img/2.png)

________________________________________________________________________________________________________________________________________________________________________________________________________________________

Seguidament, farem un ping a les dues màquines per saber si estan conectades.

```bash
ping IP_CLIENT
```

![Capt2](img/1.1.png)

![Capt3](img/1.png)

```bash
ping IP_SERVIDOR
```

________________________________________________________________________________________________________________________________________________________________________________________________________________________

Ara, dins del servidor, crearem dos grups devs i admins

```bash
sudo groupadd devs
```
```bash
sudo groupadd admins
```

![Capt4](img/3.png)

________________________________________________________________________________________________________________________________________________________________________________________________________________________

Tot seguit, crearem dos usuaris:

```bash
sudo adduser dev01
```
```bash
sudo adduser admin01
```
![Capt5](img/4.png)

![Capt6](img/5.png)

________________________________________________________________________________________________________________________________________________________________________________________________________________________

Crearem els seguents directoris:

```bash
sudo /srv/nfs/dev_projectes
```
```bash
sudo /srv/nfs/admin_tools
```

![Capt7](img/6.png)

![Capt8](img/7.png)

________________________________________________________________________________________________________________________________________________________________________________________________________________________

El grup Devs tindra control total sobre els seus projectes El grup Admins tindra control total sobre les seves eines l'usuari propietari de tots dos casos serà root.

```bash
sudo chown root:devs /srv/nfs/dev_projectes/
```
```bash
sudo chown root:admins /srv/nfs/admin_tools/
```
```bash
sudo chmod 770 /srv/nfs/dev_projectes/
```
```bash
sudo chmod 770 /srv/nfs/admin_tools/
```
Ara, aquesta comanda per comprobar els permisos

```bash
ls -la /srv/nfs/
```

![Capt9](img/8.png)
