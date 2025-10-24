# Fase 2: Guia d'Ús Tècnica (Manual Operatiu)

---

Per instalar bitwarden haurem de buscar bitwarden descargar o bitwarden download, seleccionar l'opció de portable app for Flash Drives una vegada se'ns instal·li l'arxiu obrirem i ja tindrem bitwarden instal·lat.

---

Iniciar sessió a bitwarden amb el nostre correu.

![instalacio bitwarden](/T01Gestordecontrasenyes/img/T01.1.png)

---

Una vegada iniciem sessió a bitwarden tindrem aquest menu.

---

Per utilitzar el generador de contrasenyes s’ha de clicar a l’apartat **mostra**, i seguidament clicar a **generador**, s’obrira aquest menú on podem seleccionar la longitud i els tipus de caràcters de la contrasenya.

---

### Com desar una credencial d'un compte de correu electrònic.

Per desar una credencial d'un compte de correu electrònic s’ha de clicar al **+**, i després a **inici de sessió**, després haurem de completar tots els apartats que és soliciten.

---

Una vegada complerts tots els apartats clicarem a **guarda** i ja tindrem el nostre credencial d'un compte de correu electrònic.

---

### Com desar una credencial d'una aplicació o servei web:

Per desar una credencial d'una aplicació o servei web haurem de clicar al signe de **+** a la part inferior de la pantalla i seleccionar l’opció d'**inici de sessió** i després haurem de completar tots els apartats que és soliciten.

---

Una vegada complerts tots els apartats clicarem a **guarda** i ja tindrem una credencial d'una aplicació o servei web.

---

### Com fer servir l’extensió del navegador per emplenar automàticament les dades:

Primer entrem a la **Chrome Web Store**, busquem **Bitwarden** i l’instalem.

Després iniciem sessió amb el mateix correu i contrasenya que hem utilitzat anteriorment.

I ja tindrem **Bitwarden** com una extensió.

---

## 4. Gestió de Còpies de Seguretat (Backup):

**Explicació detallada de com fer una còpia de seguretat de l'arxiu de contrasenyes (KDBX en KeePass o Exportació en Bitwarden).**

Per fer una còpia de seguretat de l'arxiu de contrasenyes a Bitwarden haurem de clicar a l’apartat de **fitxer** i **exporta caixa forta**.

---

Després seleccionarem el format de l’exportació:

- **.JSON:** format recomanat, manté tota la informació estructurada.  
- **.CSV:** format més senzill, però menys segur (evita’l si pots).

---

Després introduirem la **contrasenya mestra** per confirmar la identitat.

I una vegada fet això, **desa el fitxer exportat** al teu ordinador.  
Aquest fitxer conté totes les teves contrasenyes en text llegible, així que **no l’has de deixar sense protecció!**

---

### Bones pràctiques per desar la còpia de seguretat:

Per garantir la màxima seguretat, és recomanable seguir aquestes pautes:

- No deixis mai la còpia al teu ordinador sense xifrar.  
  Si algú accedeix al teu equip, podria llegir totes les contrasenyes.
- Emmagatzema la còpia en un lloc segur, com:
  - Una clau USB xifrada, protegida amb contrasenya.
  - Un disc extern protegit amb **BitLocker** (Windows) o **FileVault** (Mac).
  - Un servei de núvol amb xifratge d’extrem a extrem, com ara **Tresorit**, **Sync.com** o **MEGA**.
- Fes còpies periòdiques, especialment si afegeixes o modifiques moltes contrasenyes.
- No comparteixis mai el fitxer d’exportació ni la teva contrasenya mestra amb ningú.

---

Per restaurar una còpia de seguretat, clica a **fitxer** i després a **importa dades**.

Selecciona el mateix format en què vas fer la còpia (**.JSON** o **.CSV**).  
Carrega el fitxer i totes les contrasenyes es tornaran a importar automàticament.

