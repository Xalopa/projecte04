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

![Capt3](img/1.png)w

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
Ara, amb aquesta comanda comprobarem els permisos:

```bash
ls -la /srv/nfs/
```

![Capt9](img/8.png)

________________________________________________________________________________________________________________________________________________________________________________________________________________________

Tot seguit, instal·larem el servei NFS:

```bash
sudo apt install nfs-kernel-server
```

![Capt10](img/0.png)

I l'haurem d'habilita el serveri NFS

```bash
sudo systemctl enable nfs-kernel-server
```

```bash
sudo systemctl start nfs-kernel-server
```

```bash
sudo systemctl system nfs-kernel-server
```

![Capt11](img/9.png)

________________________________________________________________________________________________________________________________________________________________________________________________________________________

Ara al Client haurem de configurar amb les mateixes gid i uid els usuaris i grups.
Primer de tot, en el servidor, haurem d'executar la seguent comanda i ens haurem d'apuntar el que ens diu:

```bash
id admin01 && id dev01
```
![Capt12](img/10.png)

Un cop haber apuntat tot, anirem a la màquina del client, i executarem les seguents comandes:

```bash
sudo groupadd -g 1002 admins
sudo groupadd -g 1001 devs
```

![Capt13](img/11.png)

```bash
sudo adduser --uid 1004 admin01
sudo adduser --uid 1003 dev01
```

![Capt14](img/12.png)

![Capt15](img/13.png)

```bash
sudo usermod -a -G admins admin01
sudo usermod -a -G devs dev01
```

![Capt16](img/14.png)

I per verificar que esta tot correctament:

![Capt17](img/15.png)

________________________________________________________________________________________________________________________________________________________________________________________________________________________

Seguidament, haurem d'instal·lar nfs que necessitem

```bash
sudo apt install nfs-common -y
```

![Capt18](img/16.png)

________________________________________________________________________________________________________________________________________________________________________________________________________________________

Al servidor, modificarem l'arxiu /etc/exports per permetre exportar el nostre directori

```bash
sudo nano /etc/exports
```
![Capt19](img/17.png)

![Capt20](img/18.png)

Si anem a la màquina del client, podrem verificar que esta exportant al servidor

```bash
sudo showmount -e 10.0.2.10
```

![Capt21](img/19.png)

Ara si, podem muntar el directori del servidor a un dels directoris del client

```bash
sudo mount -t nfs 10.0.2.6:/srv/nfs/admin_tools /mnt/admin_tools/
```

![Capt22](img/20.png)

Comprobem com els arxiu estan disponibles en el directori on hem muntat els arxius, podem fer-ho amb comandes (ls) o des del gui.

![Capt23](img/21.png)

Ara configurem el client per a que es monti automàticament la nostra carpeta al iniciar sessió. Això ho farem editant l'arxiu /etc/fstab

```bash
sudo nano /etc/fstab
```

![Capt24](img/22.png)

Ara com a pas final caldrà fer el mateix per a el directori de devs (muntar-lo i configurar)
Des del servidor afegim una nova línea a l'arxiu /etc/exports per configurar el directori.
Afegim:

```bash
/srv/nfs/dev_projects/ 10.0.2.9(rw,sync,no_subtree_check,no_root_squash)
```

![Capt25](img/23.png)

Seguidament, hauriem de fer el maeix procés per l'altre group, ara podriem veure com l'arxiu s'ha creat correctament:

![Capt26](img/24.png)




