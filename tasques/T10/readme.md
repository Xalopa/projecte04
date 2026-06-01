# 🖨️ T10 · Servidor d’impressió Linux: CUPS (tasca individual)

---

# 📘 Breu descripció

## 🧠 Introducció

A EverPia treballem per optimitzar els recursos dels clients i reduir la complexitat dels seus entorns.

Un dels problemes més habituals en entorns d’oficina és la gestió d’impressió:

- 🖨️ Impressores mal configurades
- 💾 Drivers incompatibles
- 💸 Consum i costos descontrolats
- 📍 Usuaris enviant treballs a impressores incorrectes

---

## 🎯 Solució professional

La solució és un:

> 🖨️ **Servidor d’impressió centralitzat**

---

# 🏢 Cas client: DevOptimize Solutions

El client necessita una solució per:

- Centralitzar la impressió
- Simplificar la gestió d’impressores
- Donar servei a clients Linux (Zorin OS) i servidors Ubuntu

---

# 🧪 La Vostra Missió: Prova de Concepte (PoC)

## 🎯 Objectiu

Demostrar que un servidor Linux pot:

- Gestionar una impressora
- Compartir-la en xarxa
- Rebre treballs d’impressió de clients remots

---

## 🖨️ Impressora virtual

Per evitar hardware físic s’utilitza:

> 📄 **cups-pdf**

Aquesta eina:

- Simula una impressora real
- Genera fitxers PDF al servidor
- Permet validar el flux d’impressió

---

# 🖥️ Escenari de treball

## 🧱 Infraestructura

### 🖥️ Servidor (Ubuntu Server)

- NAT
- Xarxa Host-Only
- Servei CUPS instal·lat

---

### 💻 Client (Zorin OS)

- Mateixa xarxa que el servidor
- Connexió a la impressora compartida

---

# ⚙️ Fases de la PoC

## 1️⃣ Instal·lació de CUPS

- Instal·lació del servei d’impressió
- Activació del servei

---

## 2️⃣ Impressora virtual

- Instal·lació de `cups-pdf`
- Configuració de la impressora

---

## 3️⃣ Configuració del servei

- Permetre connexions remotes
- Configurar escolta en totes les interfícies

---

## 4️⃣ Interfície web de CUPS

- Accés via navegador
- Compartició de la impressora

---

## 5️⃣ Configuració del client

- Afegir impressora des de Zorin OS
- Connexió al servidor CUPS

---

## 6️⃣ Proves d’impressió

- Enviament de documents
- Verificació de la cua d’impressió

---

## 7️⃣ Validació al servidor

- Comprovació de fitxers PDF generats
- Verificació del flux complet

---

# 📋 Documentació obligatòria

La pràctica ha d’incloure:

- 💻 Comandes utilitzades
- ⚙️ Configuracions realitzades
- 📸 Captures de pantalla
- 🧪 Evidència de funcionament
- 🖨️ Resultats d’impressió

---

# 🎯 Objectiu final

Aquesta PoC ha de demostrar:

- 🖨️ Impressió centralitzada funcional
- 🌐 Accés remot des de clients
- ⚙️ Gestió eficient del servei
- 💸 Reducció de costos i complexitat

---

# 📚 Materials de suport

- 📘 UD5 AA1 · CUPS · Moodle (Sistemes Operatius en Xarxa)
- 🎥 https://www.youtube.com/watch?v=FNwSTrOSgZQ
- 📄 https://documentation.ubuntu.com/server/how-to/networking/install-nfs/
- 🔧 https://idroot.us/install-cups-print-server-ubuntu-24-04/
