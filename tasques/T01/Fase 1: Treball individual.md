# 📁 Fase 1 — Treball Individual  
Document de planificació de còpies de seguretat elaborat per: **Pol, Xavi, Blai i Pau**.

---

## 📑 Índex
1. [FASE 1 — Pol](#fase-1--pol)
2. [FASE 1 — Xavi](#fase-1--xavi)
3. [FASE 1 — Blai](#fase-1--blai)
4. [FASE 1 — Pau](#fase-1--pau)

---

## FASE 1 — Pol

### Què copiarem?
- Bases de dades (crítiques i d’ús diari).  
- Documents de Projectes (plànols i especificacions).  
- Carpetes **Documents** dels usuaris.  

> No es copia tot l’equip client per evitar dades innecessàries. Només les carpetes *Documents*.

### Cada quan i com?
- **Bases de dades**  
  - Incremental cada 4 h  
  - Completa setmanal  
- **Projectes i carpetes personals**  
  - Diferencial diària  
  - Completa setmanal  
- **Equips clients**  
  - Incremental o sincronització diària  

### Mitjans i ubicació
- NAS local  
- Còpia al núvol (Azure, Google Cloud…)  
- Discos externs (SSD, HDD, cintes)  

### Regla 3-2-1
- 3 còpies  
- 2 tipus de mitjans  
- 1 fora de lloc  

---

## FASE 1 — Xavi

### Dades a copiar
- Bases de dades (20 GB)  
- Documents de Projectes (300 GB)  
- Carpetes Personals (100 GB)  
- Equips clients: només carpetes *Documents*

### Periodicitat i tipus de còpia
**Bases de Dades**
- Incremental cada 4 h  
- Completa diària  

**Documents de projectes**
- Incremental diària  
- Completa setmanal  

**Carpetes personals**
- Incremental diària  
- Completa setmanal  

### Històric
- Retenció mínima d’1 mes

### Mitjans i ubicació
- NAS local  
- Núvol per còpia externa  
- Discos externs per arxiu mensual/setmanal  

### Regla 3-2-1
- 3 còpies  
- 2 mitjans  
- 1 còpia al núvol  

---

## FASE 1 — Blai

### Què copiarem?
- Bases de dades (clients, factures…)  
- Fitxers compartits (documents, projectes)  
- Configuració del servidor (usuaris, permisos)  
- Màquines virtuals, si n’hi ha  
- Logs importants  
- Només equips clients amb dades locals importants

### Cada quan i com?
- **Incremental diària**  
- **Diferencial setmanal**  
- **Completa mensual**  

### Mitjans i ubicació
- Discs durs externs  
- NAS  
- Còpia al núvol  
- Cintes (si cal molta retenció)

### Regla 3-2-1
- 3 còpies  
- 2 mitjans diferents  
- 1 fora de lloc  

---

## FASE 1 — Pau

### Què copiarem?
- Documents de projectes  
- Base de dades de Comptabilitat i Clients  
- Carpetes personals dels usuaris  
- Carpetes rellevants d’equips clients

### Cada quan i com?
- Incremental diària per Comptabilitat i Clients  
- Completa setmanal del servidor  
- Diferencial diària de documentació i carpetes personals  
- Completa mensual de totes les dades (retenció ≥ 1 mes)

### Mitjans i ubicació
- NAS local  
- Còpia al núvol com a protecció extra  

---

## ✔️ Estat del document
Aquest README.md està pensat per ser utilitzat com a documentació del projecte de còpies de seguretat de la *Fase 1*.


