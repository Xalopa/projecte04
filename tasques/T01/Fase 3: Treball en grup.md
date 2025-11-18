# Fase 3: Treball en Grup

## 1. Debat i Selecció

Durant el debat de grup sobre les propostes de les parelles, es van destacar els següents punts:

- **Coincidències entre les propostes:**
  - Prioritzar les dades més crítiques: bases de dades, documents de projecte i carpetes personals.
  - No fer còpia completa dels equips clients, només de les carpetes clau.

- **Pros i contres de cada proposta:**
  - **Parella Pol i Pau:** 
    - Més fàcil d’implementar i administrar diàriament.
    - Permet recuperació ràpida per a la majoria d’incidents.
    - Cost assumible per una empresa petita.
  - **Parella Xavi i Blai:** 
    - Periodicitat adaptada a RPO/RTO.
    - Inclou còpies a llarg termini i diversificació de mitjans.
    - Major robustesa, però amb més complexitat i cost.

---

## 2. Política de Còpies de Seguretat Definitiva

La política de còpies de seguretat per a **Muntatges i Serveis Tècnics SL** és la següent:

### Dades a Copiar
- Bases de dades de Comptabilitat i Clients.
- Documents de projectes.
- Carpetes personals dels usuaris.

### Tipus i Periodicitat de les Còpies
- **Comptabilitat i Clients:**
  - Còpia incremental diària.
  - Còpia completa setmanal.
- **Documentació i carpetes personals:**
  - Còpia diferencial diària.
  - Còpia completa mensual (garantint retenció mínima d’un mes).

### Mitjans i Ubicació
- **Mitjà principal:** NAS local a l’oficina per a recuperació ràpida.
- **Còpia addicional:** Cloud per garantir recuperació fora del lloc en cas d’incident greu.

### Objectius
- Assegurar la **disponibilitat** i **seguretat** de les dades.
- Complir amb els requisits de l’empresa.
- Garantir recuperació ràpida en incidents habituals i protecció contra desastres majors.

---



