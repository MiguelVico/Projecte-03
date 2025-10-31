# 🧩 T06: Fonaments del Servei DNS

## 🏢 Context de l’activitat

Com a membres de l’equip tècnic de **EverPia**, heu rebut un nou encàrrec del vostre client **DigiCore**, una empresa de màrqueting digital que experimenta errors de connectivitat en algunes aplicacions.  
L’equip tècnic sospita que aquests problemes podrien estar relacionats amb una **resolució de noms DNS incorrecta o lenta**.

La vostra missió és **realitzar una auditoria teòrica i pràctica** del servei DNS per formar el personal del client i proporcionar-los **eines de diagnosi eficients**.

---

## 📘 Fase Teòrica: Sessió Formativa

En aquesta primera fase, cal preparar **una píndola formativa en format vídeo (10-15 minuts)** per al personal de DigiCore.  
L’objectiu és explicar de forma clara i visual els **conceptes fonamentals del servei DNS**.

### 📚 Continguts a treballar

1. **Jerarquia i Estructura del DNS**
   - Estructura en arbre: *Root → TLDs → Segon nivell*.
2. **Procés de Resolució**
   - Diferència entre consultes **iteratives** i **recursives**.  
   - Què són els **servidors Root** i **autoritatius**.
3. **Tipus de Zones**
   - **Directa** i **inversa**.  
   - **Primària** i **secundària**.
4. **Tipus de Registres (Records)**
   - `A`, `CNAME`, `MX`, `NS`, `SRV`.
5. **Conceptes Essencials**
   - **Resposta autoritativa:** què significa i com identificar-la.  
   - **TTL (Time To Live):** funció i impacte en la propagació i rendiment.  
   - **SOA (Start of Authority):** informació essencial i importància.  
   - **Reenviadors:** condicionals i incondicionals.  
   - **Resolució local:** mecanismes sense servidor (protocol **mDNS**).

🧠 **Activitat:** Preparar i gravar un vídeo formatiu de 10 a 15 minuts explicant tots aquests conceptes.

---

## 💻 Fase Pràctica: Diagnosi de Noms (Auditoria amb CLI)

A la segona fase, posareu en pràctica els coneixements adquirits fent **proves reals amb eines de diagnosi DNS** en diferents sistemes operatius (**Linux/macOS i Windows**).

L’escenari de treball és un equip **Zorin OS** amb:
- 1a interfície en **NAT**
- 2a interfície en **Adaptador pont**, amb IP configurada segons les indicacions del responsable.

---

### 🧪 A. Diagnosi avançada amb `dig` (Linux / macOS)

| Nº | Comanda | Objectiu | Anàlisi esperada |
|----|----------|-----------|------------------|
| 1 | `dig xtec.cat A` | Consulta bàsica de registre A | Identificar IP, TTL i servidor que respon. |
| 2 | `dig tecnocampus.cat NS` | Consulta de servidors de noms | Llistar els servidors de noms autoritatius. |
| 3 | `dig escolapia.cat SOA` | Consulta detallada SOA | Localitzar correu de l’administrador i número de sèrie. |
| 4 | `dig -x 147.83.2.135` | Consulta inversa | Analitzar quina informació retorna. |

---

### 🧩 B. Comprovació de resolució amb `nslookup` (Windows / Multiplataforma)

L’eina `nslookup` permet fer consultes DNS tant de forma directa com interactiva (`>`).

Comandes útils:
- `set type=` → per definir el tipus de consulta (`A`, `MX`, `NS`, `SOA`, etc.)
- `server IP` → per especificar el servidor DNS.
- `exit` → per sortir del mode interactiu.

#### 🔹 Comanda 1: Consulta bàsica no autoritativa
- **Tipus:** `A`
- **Domini:** `tecnocampus.cat`
- **Anàlisi:** Explicar per què la resposta no és autoritativa.

#### 🔹 Comanda 2: Consulta autoritativa
- **Servidor:** IP del primer servidor de noms obtingut anteriorment.
- **Consulta:** `A` de `tecnocampus.cat`
- **Anàlisi:** Comparar amb la resposta anterior i destacar les diferències.

---

### 🌐 C. Resolucions locals

Proves del funcionament de la **resolució local**, útil en xarxes internes sense servidor DNS propi, fent servir **mecanismes de resolució entre equips** (com mDNS).

---

## 🧾 Activitat final: Documentació dels resultats

Cal crear un document anomenat **`guia.md`** que inclogui:
- Les **captures de pantalla** de totes les comandes executades (`dig` i `nslookup`).
- Una **anàlisi breu** per a cada resultat.
- Les **proves i resultats** de la resolució local.

---

## 🧱 Lliurament

El lliurament final constarà de:
1. 📹 **Vídeo formatiu (10-15 min)** — Fase Teòrica  
2. 🗒️ **guia.md** amb captures i anàlisis — Fase Pràctica

---

## 🧭 Objectius d’aprenentatge

- Comprendre el **funcionament i estructura del sistema DNS**.  
- Saber diferenciar i analitzar **consultes recursives, iteratives i autoritatives**.  
- Utilitzar **eines de diagnosi** com `dig` i `nslookup`.  
- Documentar correctament resultats tècnics i conclusions.

---

✍️ **Autor:** *Equip tècnic d’EverPia*  
📅 **Activitat:** T06 – Fonaments del Servei DNS  
🏫 **Client:** DigiCore

