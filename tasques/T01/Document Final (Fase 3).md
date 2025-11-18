# Document Final: Política de Còpies de Seguretat (Fase 3)

## 1) Dades Objecte de Còpia

### Servidor

| Tipus de Dada                  | Crítica | Freqüència de Còpia                                     |
|--------------------------------|---------|--------------------------------------------------------|
| Bases de Dades (Comptabilitat/Clients) | ✅      | Incremental cada 4 h + completa diària + còpia mensual completa |
| Documents de Projectes          | ✅      | Incremental diària + completa setmanal + còpia mensual completa |
| Carpetes Personals dels Usuaris | ❌      | Diferencial diària + còpia mensual completa           |

### Clients

| Tipus de Dada                | Crítica        | Freqüència de Còpia                           |
|-------------------------------|----------------|-----------------------------------------------|
| Documents locals temporals    | ❌             | No es copia (recomanat guardar al servidor) |
| Configuracions especials      | ✅ (si n’hi ha) | Còpia puntual si són difícils de recuperar   |

### Resum de Dades i Frequència

- **Servidor:**
  - **Dades Crítiques:** Base de dades de Comptabilitat i Clients, documents de projectes → Incremental diària, completa setmanal, completa mensual.
  - **Dades No Crítiques:** Carpetes personals dels usuaris → Diferencial diària, completa mensual.
- **Clients:**
  - **Dades Crítiques:** Només carpetes clau dels tècnics → Diferencial diària, completa mensual.
  - **Dades No Crítiques:** Resta dels fitxers no es copien, ja que la informació important està centralitzada al servidor.

---

## 2) Cronograma Setmanal Detallat

| Dia       | Dades                              | Tipus de Còpia | Mitjà       |
|-----------|------------------------------------|----------------|------------|
| Dilluns   | Comptabilitat/Clients, documents de projectes | Incremental     | NAS        |
|           | Carpetes personals dels usuaris     | Diferencial     | NAS        |
| Dimarts   | Comptabilitat/Clients, documents de projectes | Incremental     | NAS        |
|           | Carpetes personals dels usuaris     | Diferencial     | NAS        |
| Dimecres  | Comptabilitat/Clients, documents de projectes | Incremental     | NAS        |
|           | Carpetes personals dels usuaris     | Diferencial     | NAS        |
| Dijous    | Comptabilitat/Clients, documents de projectes | Incremental     | NAS        |
|           | Carpetes personals dels usuaris     | Diferencial     | NAS        |
| Divendres | Comptabilitat/Clients, documents de projectes | Incremental     | NAS        |
|           | Carpetes personals dels usuaris     | Diferencial     | NAS        |
| Dissabte  | Comptabilitat/Clients, documents de projectes | Incremental     | NAS        |
|           | Carpetes personals dels usuaris     | Diferencial     | NAS        |
| Diumenge  | Tot el servidor i dades clients     | Completa        | NAS + Cloud|

---

## 3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

- **Mitjà 1 (Local):** NAS ubicat a l’oficina, centralitzant totes les còpies i permetent recuperació ràpida.
- **Mitjà 2 (Extern):** Cloud segur (Microsoft Azure, Google Cloud), per còpia fora del lloc i alta disponibilitat.
- **Ubicació Fora de Lloc:** Cloud gestionat pel proveïdor, supervisat pel responsable de sistemes, assegurant accessibilitat i seguretat en cas d’incident.

---

## 4) Estratègia de Recuperació (RTO/RPO)

- **RPO (Recovery Point Objective):**  
  Per a les dades de Comptabilitat i Clients, es realitzen còpies incrementals cada 4 hores per capturar els canvis més recents i minimitzar pèrdues.

- **RTO (Recovery Time Objective):**  
  La recuperació es fa principalment des del NAS local per accés immediat, amb còpia al Cloud com alternativa si el servidor local no està disponible. Això garanteix una restauració ràpida i mínima interrupció del funcionament de l’empresa.

---


