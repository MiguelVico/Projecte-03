
# **P04 – Documentació del Servidor DNS**

Aquest projecte recull tota la configuració creada durant la tasca de muntatge d’un servidor DNS a Ubuntu Server. L’objectiu principal és tenir una còpia clara, ordenada i reutilitzable de tots els fitxers necessaris perquè qualsevol persona pugui replicar el servidor fàcilment en un altre sistema, simplement descarregant-los i reiniciant el servei.

## 📌 **Descripció de la tasca**

Com a consultors del departament de sistemes d’EverPia, hem preparat un servidor DNS com a prova de concepte per al client **Digicore**. Inicialment, la configuració es trobava dins d’una màquina virtual, però per garantir-ne la reutilització i la documentació correcta, cal pujar-la a GitHub.

Això ens permet:

* Disposar d’una còpia segura i versionada.
* Evitar repetir el procés de configuració des de zero.
* Reutilitzar els fitxers per desplegar el servidor en altres màquines.
* Treballar amb bones pràctiques de documentació i control de versions.

---

## 🔧 **Fase 1 – Preparació i Extracció dels Fitxers**

### **1.1 Configuració de la Interfície Host-Only**

Per poder copiar fitxers des de la màquina virtual a l’ordinador físic, s’ha afegit una **segona interfície de xarxa** en mode *Host-Only*.
Aquesta interfície permet la connexió directa entre host i VM.

Un cop configurada:

* Es comprova la connectivitat amb `ping`.
* Es valida que la màquina física pot accedir a la VM.

### **1.2 Transferència de fitxers amb SCP**

Un cop la connexió Host-Only funciona, s’utilitza la comanda **scp** per copiar els fitxers de configuració DNS:

**Fitxers copiats:**

```
/etc/bind/named.conf.options  
/etc/bind/named.conf.local  
/etc/bind/zones/ (tots els arxius de zones)
```

**Exemple de comanda scp:**

```
scp usuari@IP_VM:/etc/bind/named.conf.options .
```

El punt final (`.`) indica que el fitxer es copiarà al directori actual de la màquina física.

---

## 🚀 **Fase 2 – Integració amb GitHub**

### **2.1 Creació del directori producte04 i del README.md**

Dins del repositori, es crea:

```
producte04/
└── README.md
```

En aquest fitxer (el que estàs llegint), s’explica el contingut i l’objectiu de la tasca.

### **2.2 Pujar els fitxers de configuració**

* Es crea la carpeta `zones/` dins `producte04/`.
* Es poden utilitzar fitxers temporals com `zones/esborrar` per poder crear la carpeta a GitHub.
* Finalment, s'hi pugen tots els fitxers DNS corresponents.

---

## 🎯 **Objectiu de la tasca**

Documentar i versionar la configuració d’un servidor DNS utilitzant GitHub, remarcant la importància de la **repetitibilitat**, és a dir, la capacitat de reproduir la configuració de forma ràpida i segura.

---

## 🧩 **Competències treballades**

* Elaboració de documentació tècnica clara i ordenada.
* Ús de terminologia tècnica estàndard del sector.
* Ús del control de versions per gestionar configuracions de sistema.

---

## 🏁 **Resultats d’aprenentatge (RA)**

**1716.RA 5** – Transmetre informació de manera clara, estructurada i ordenada.

### **Criteris d'Avaluació relacionats**

* **5.1** Manté una actitud ordenada i metòdica en la transmissió d’informació.
* **5.4** Coneix i utilitza termes tècnics en altres llengües quan són estàndards del sector.

---

## 🛠️ **Capacitats clau treballades**

* Autonomia
* Innovació
* Organització del treball
* Responsabilitat
* Treball en equip
* Relació interpersonal
* Resolució de problemes


