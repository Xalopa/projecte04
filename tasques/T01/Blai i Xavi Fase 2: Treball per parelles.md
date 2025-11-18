# Fase 2: Treball per Parelles

## 1. Discussió i Consens

A continuació es mostra la comparació entre les respostes de **Xavi** i **Blai** sobre la Fase 1.

### Comparativa de Propostes

| **Aspecte** | **Resposta (Xavi)** | **Resposta (Blai)** | **Coincidències / Diferències** |
|-------------|---------------------|-----------------------|----------------------------------|
| **Què copiar** | Bases de dades (prioritat màxima), documents de projectes, carpetes personals. No cal còpia completa dels 10 clients. | Bases de dades, documents, configuració del servidor, comptes d’usuari, permisos, màquines virtuals, logs. No cal còpia completa dels 10 clients. | Coincidim en no copiar tots els clients. Xavi se centra en dades d’ús diari; Blai afegeix configuracions i logs. |
| **Periodicitat** | BD: incremental cada 4 h + completa diària. Documents i carpetes: incremental diària + completa setmanal. | Incremental diària (dl–dv), diferencial setmanal (ds), completa mensual. | Diferència clara: Xavi compleix RPO de 4 h; Blai presenta un esquema estàndard però no compleix el RPO. |
| **Tipus de còpia** | Incremental + completa (segons necessitat). | Incremental + diferencial + completa. | Xavi adapta les còpies als RTO/RPO; Blai aplica un esquema general. |
| **Mitjans i ubicació** | NAS local + Cloud + discos externs (regla 3-2-1). | Discos externs + NAS + Cloud + cintes (regla 3-2-1). | Xavi aplica una solució moderna i pràctica; Blai afegeix cintes per retencions llargues. |

---

## 2. Proposta Unificada — Esquema 3-2-1

Després del consens, es presenta la proposta definitiva de còpies de seguretat:

### Esquema 3-2-1 (Proposta de la Parella)

| **Element** | **Proposta de la Parella** | **Justificació** |
|-------------|----------------------------|-------------------|
| **Dades Crítiques** | Bases de dades de Comptabilitat i Clients, Documents de Projectes, Carpetes Personals | Són dades essencials per al funcionament diari. Les BD tenen requisits estrictes de RTO i RPO. |
| **Periodicitat (BD)** | Còpia incremental cada 4 hores + còpia completa diària | Garantir que no es perdin més de 4 hores de feina i facilitar una restauració ràpida. |
| **Tipus de Còpia (BD)** | Incremental + completa | Les incrementals són ràpides i eficients; les completes creen punts ferms de restauració. |
| **Mitjà 1 (Local)** | NAS local | Accés immediat i restauració ràpida en cas d’error o pèrdua de dades. |
| **Mitjà 2 (Extern)** | Cloud (còpia fora de l’empresa) | Protecció davant desastres físics (incendis, robatoris) i disponibilitat remota. |

---

## ✔️ Resum Final

La proposta unifica la precisió i els requisits estrictes (RPO de 4 h) de Xavi amb alguns aspectes robustos del model de Blai, tot mantenint una arquitectura clara 3-2-1 basada en:

- NAS local com a mitjà primari  
- Cloud com a còpia fora de lloc  
- Còpies incrementals freqüents + completes diàries/setmanals  



