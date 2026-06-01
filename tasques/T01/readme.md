# 💾 T01 · DRP: còpies de seguretat (Estudi de cas client)

---

# 📘 Breu descripció

## 📌 Introducció

La primera hora, el responsable de seguretat presenta el tema de les **còpies de seguretat** a partir de material didàctic.

A continuació, es treballa el contingut mitjançant una **dinàmica cooperativa**.

---

# 🏢 Presentació del cas client

## 📁 Empresa: *Muntatges i Serveis Tècnics SL*

Petita empresa dedicada a la instal·lació i manteniment d’equips industrials.

---

## 🖥️ Infraestructura tècnica

### 🗄️ Servidor de fitxers (Ubuntu Server)

Conté informació crítica:

* 📐 Documents de projectes (300 GB)
* 🧾 Bases de dades (comptabilitat i clients) (20 GB)
* 👤 Carpetes personals d’usuaris (100 GB)

---

### 💻 Equips clients

* 10 equips Windows 10/11
* Ús principal: accés a fitxers del servidor
* Alguns usuaris guarden fitxers locals temporals

---

### 🌐 Connexió

* Fibra òptica simètrica de 600 Mbps

---

## 🎯 Requisits de recuperació

| Concepte     | Requisit                                    |
| ------------ | ------------------------------------------- |
| 🕒 RTO       | < 4 hores per BD de clients/comptabilitat   |
| 📉 RPO       | Màxim 24 hores (general) / 4 hores (crític) |
| 🗂️ Retenció | Mínim 1 mes d’històric                      |

---

# 🧠 Fase 1 · Treball individual

## ❓ 1. Què copiar? (priorització)

* Identificació de dades més crítiques del sistema
* Avaluació si cal fer còpia dels 10 equips clients
* Justificació de decisions

---

## 🔁 2. Periodicitat i tipus de còpia

Proposta de planificació:

* 📅 Diària
* 📆 Setmanal
* 🗓️ Mensual

Tipus de còpies:

* 💾 Completa
* 🔄 Diferencial
* ➕ Incremental

---

## 📦 3. Mitjans i ubicació (Regla 3-2-1)

Anàlisi de:

* 💽 Discs durs externs
* 🗄️ NAS
* ☁️ Cloud
* 📼 Cintes

### 📌 Regla 3-2-1:

* 3 còpies
* 2 mitjans diferents
* 1 còpia fora de l’entorn local

---

# 👥 Fase 2 · Treball per parelles

## 🤝 1. Discussió i consens

* Comparació de respostes individuals
* Posada en comú de criteris

---

## 🧩 2. Proposta unificada (Esquema 3-2-1)

| Element              | Proposta de la parella | Justificació |
| -------------------- | ---------------------- | ------------ |
| 📂 Dades crítiques   |                        |              |
| ⏱️ Periodicitat BD   |                        |              |
| 💾 Tipus de còpia BD |                        |              |
| 🖥️ Mitjà 1 (local)  |                        |              |
| ☁️ Mitjà 2 (extern)  |                        |              |

---

# 👨‍👩‍👧‍👦 Fase 3 · Treball en grup

## 🗣️ 1. Debat i selecció

Cada parella presenta la seva proposta i es valora:

* 💰 Cost
* ⏱️ Temps de recuperació
* 🔐 Seguretat
* 🧠 Simplicitat

---

## 🏗️ 2. Política final de còpies

Redacció de la **política definitiva de backups** per a:

> 🏢 *Muntatges i Serveis Tècnics SL*

---

# 📄 Document final (Fase 3)

## 1️⃣ Dades objecte de còpia

* Separació servidor / clients
* Distinció entre dades crítiques i no crítiques
* Freqüència de còpia

---

## 2️⃣ Cronograma setmanal

| Dia       | Dades | Tipus de còpia | Mitjà |
| --------- | ----- | -------------- | ----- |
| Dilluns   |       |                |       |
| Dimarts   |       |                |       |
| Dimecres  |       |                |       |
| Dijous    |       |                |       |
| Divendres |       |                |       |
| Dissabte  |       |                |       |
| Diumenge  |       |                |       |

---

## 3️⃣ Elecció de mitjans (Regla 3-2-1)

* 💽 **Mitjà 1 (local):** suport físic intern o NAS
* ☁️ **Mitjà 2 (extern):** cloud o servei extern (Azure, Google Cloud, etc.)
* 📍 **Fora de lloc:** ubicació externa o servidor remot gestionat

---

## 4️⃣ Estratègia de recuperació (RTO / RPO)

* Garantia de RPO ≤ 4 hores per dades crítiques
* Garantia de RTO ≤ 4 hores en restauració
* Procediments de recuperació definits i provats

---

# 📚 Materials de suport

* Moodle 0226 Seguretat Informàtica · RA2.AA3 Còpies
* INCIBE · Guia de còpies de seguretat
* 🎥 Xataka: Backup 3-2-1
  https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8

---

# 🎯 Objectiu final

Dissenyar una **estratègia de còpies de seguretat realista, coherent i professional**, capaç de garantir:

* 🔐 Seguretat de dades
* ⏱️ Recuperació ràpida
* 📊 Continuïtat del negoci

