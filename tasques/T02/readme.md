# 💾 T02 · DPR: còpies de seguretat (Cas pràctic)

---

# 📘 Breu descripció

## 🧩 Introducció al cas

A la tasca anterior es va dissenyar una política de còpies de seguretat per al client:

> 🏢 **Muntatges i Serveis Tècnics SL**

Ara cal portar aquesta proposta a la pràctica mitjançant **guies tècniques i proves de concepte**, amb l’objectiu de formar el personal per implementar el sistema de backups.

---

# 🪟 PART 1 · Còpia de seguretat equips Windows

## 📌 Context

Encara que el DPR no contempla habitualment còpies de seguretat d’equips clients, es fa una excepció amb:

> 💼 L’equip Windows del director de l’empresa

Aquest equip conté informació crítica que no es vol emmagatzemar al servidor.

---

## 🔐 Objectiu

Implementar una política de còpies **3-2-1**:

* 💽 Còpia local en disc secundari
* ☁️ Còpia al cloud (Google Drive)
* 🔧 Eina: **Duplicati**

---

## 🖥️ Entorn de prova

* 🪟 Màquina virtual Windows 11
* 💾 2 discos:

  * Disc 1 → Sistema operatiu
  * Disc 2 (10 GB) → Còpies de seguretat
* ☁️ Cloud → Google Drive (compte extern a l’escola)

---

## ⏱️ Política de còpies

* 📁 Cada hora → còpia al disc secundari
* 🌐 18:00 → còpia a Google Drive

---

## 🛠️ Tasques a realitzar

* Instal·lació de **Duplicati**
* Configuració de plans de backup
* Proves amb fitxers reals (carpeta Documents)
* Simulació de pèrdua de dades
* Restauració des de:

  * 💽 Disc local
  * ☁️ Cloud

---

# 🐧 PART 2 · Còpia de seguretat servidor Linux

## ⚙️ Eina utilitzada

> 🧰 **Duplicity** + cron

Permet fer còpies locals i remotes amb programació de tasques.

---

## 🖥️ Entorn de prova

* 🐧 Ubuntu Server
* 💾 Disc secundari de 10 GB (backup)
* 📁 Muntatge manual a `/media/backup`

---

## 🧪 Preparació del sistema

### 1️⃣ Preparar disc

* Inicialitzar i formatar en **xfs**
* Crear punt de muntatge:

```bash
/media/backup
```

---

### 2️⃣ Instal·lació

* Instal·lar paquet:

  * `duplicity`

---

### 3️⃣ Preparació de dades

* Crear usuaris addicionals
* Generar fitxers de prova:

  * 4 fitxers de 10 MB a `/home`

---

### 4️⃣ Backup inicial

* Còpia completa de `/home`

---

### 5️⃣ Restauració

* Eliminació de fitxers
* Recuperació amb backup

---

### 6️⃣ Backup incremental

* Afegir fitxer nou (4 MB)
* Nova còpia
* Observació de mode incremental

---

## 🔌 Gestió del disc de backup

* Desmuntar unitat després de cada còpia
* Garantir seguretat del sistema

---

# 🤖 AUTOMATITZACIÓ

## 🧾 Script 1 · fullbackup.sh

* Còpia completa de `/home`
* Emmagatzemat al volum muntat
* Ús de variable:

```bash
export PASSPHRASE=contrasenya
```

* Permisos d’execució assignats

---

## 📅 Cron (fullbackup)

```text
Diumenges · 23:00 · root
```

---

## 🧾 Script 2 · incrementalbackup.sh

* Còpies incrementals de `/home`
* Mateixa configuració de PASSPHRASE
* Permisos d’execució configurats

---

## 📅 Cron (incremental)

```text
Dilluns a dissabte · 23:00 · root
```

---

# 📚 Materials de suport

* 🔗 https://duplicati.com/
* 📄 https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/
* 📄 https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/
* 📘 http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html
* ⏱️ https://geekytheory.com/programar-tareas-en-linux-usando-crontab

---

# 🎯 Objectiu final

Implementar i validar un sistema real de còpies de seguretat que garanteixi:

* 🔐 Seguretat de dades
* ♻️ Recuperació completa
* ⚙️ Automatització amb cron
* ☁️ Integració amb cloud i sistemes locals
