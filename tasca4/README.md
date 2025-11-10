# 🧩 T04: Serveis de Directori – LDAP

## 🏢 Breu descripció

**Innovatech**, una *start-up* tecnològica en ple creixement, està patint problemes greus en la gestió dels seus **usuaris i accessos**.  
Actualment, cada servei (servidor de fitxers, wiki, etc.) utilitza la seva pròpia base de dades d’usuaris i contrasenyes, i els ordinadors clients fan servir **autenticació local**.  
Això provoca:

- ⚙️ **Ineficiència operativa**: cal crear o eliminar usuaris manualment a cada sistema.  
- 🔐 **Risc de seguretat**: reutilització de contrasenyes entre serveis.  
- 📈 **Manca d’escalabilitat**: cada nou servei complica més la gestió.

Per resoldre-ho, el **CEO d’Innovatech** ha contractat **EverPia** per implementar una **solució d’autenticació centralitzada** amb **OpenLDAP (Lightweight Directory Access Protocol)**, una eina robusta i de codi obert compatible amb GNU/Linux.

La vostra missió serà:

1. 🖥️ Instal·lar i configurar **OpenLDAP** en un servidor Linux.  
2. 🧱 Crear la jerarquia d’**unitats organitzatives (OU)**, **usuaris** i **grups**.  
3. 🔗 Configurar un **client** perquè autentiqui usuaris mitjançant el directori.

📄 Tota la feina està detallada al **plec de condicions tècniques**, disponible al Moodle de l’assignatura.

---

## 📚 Material de classe (Moodle)

- **UD04.AA1:** Serveis de Directori  
- **UD04.AA2:** Instal·lació OpenLDAP  
- **UD04.AA3:** Configuració del directori  
- **UD04.AA5:** Agregar client al directori  

---

## 🎯 Objectius específics

- Instal·lar i configurar **serveis de directori** en sistemes lliures.  
- Gestionar **objectes del directori** (OU, grups i usuaris) amb eines gràfiques i comandes.  
- Configurar **clients** per obtenir una **autenticació centralitzada**.

---

## 🧠 Competències treballades

| Codi | Descripció |
|------|-------------|
| a) | Determinar la logística d’instal·lació i manteniment de sistemes microinformàtics. |
| f) | Instal·lar, configurar i mantenir serveis multiusuari i aplicacions en xarxa. |
| l) | Assessorar i assistir el client davant necessitats tècniques. |
| q) | Col·laborar amb l’equip i complir els objectius de producció amb responsabilitat. |

---

## 📘 Resultats d’aprenentatge (RA)

- **0224.RA2:** Gestiona usuaris i grups de sistemes operatius en xarxa.  
- **0224.RA3:** Realitza tasques de gestió sobre dominis aplicant eines d’administració.

---

## 🧩 Criteris d’avaluació (CA)

### RA2 – Gestió d’usuaris i grups
- 2.1 Configura i gestiona comptes d’usuari.  
- 2.4 Distingeix el propòsit i tipus de grups.  
- 2.5 Configura i gestiona grups.  
- 2.6 Gestiona la pertinença d’usuaris a grups.  

### RA3 – Gestió de dominis
- 3.1 Identifica la funció del servei de directori i la seva nomenclatura.  
- 3.2 Reconeix el concepte de domini i les seves funcions.  
- 3.4 Instal·la el servei de directori.  
- 3.5 Realitza la configuració bàsica del directori.  
- 3.6 Utilitza agrupacions d’elements per crear models administratius.  
- 3.7 Analitza l’estructura del directori.  
- 3.8 Utilitza eines d’administració de dominis.  

---

## 🗂️ Continguts de la tasca

- **2.** Gestió d’usuaris i grups  
- **3.** Gestió de dominis  

---

## 💡 Capacitats clau treballades

- 🧭 **Autonomia**  
- 💡 **Innovació**  
- 🤝 **Relació interpersonal**  
- 📋 **Organització del treball**  
- ✅ **Responsabilitat**  
- 👥 **Treball en equip**  
- 🧩 **Resolució de problemes**

---

## 🧑‍💻 Conclusió

Aquesta activitat permet entendre com un **servei de directori centralitzat** millora la gestió d’usuaris i la seguretat dins d’una empresa. Amb OpenLDAP, Innovatech podrà escalar fàcilment, reduir riscos i simplificar les operacions del seu equip tècnic.

