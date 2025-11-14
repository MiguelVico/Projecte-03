# T03: Gestió Flexible de Discos (LVM i Espais d’Emmagatzematge)

## 📝 Descripció de la tasca
El bufet d’advocats **Garriga i Associats**, un dels més importants de la ciutat, necessita renovar els seus sistemes d’emmagatzematge per garantir **seguretat**, **alta disponibilitat** i **escalabilitat**. Gestionen informació legal molt sensible, així que qualsevol fallada seria crítica.

Com a tècnics d’Everpia, el nostre objectiu és **dissenyar i documentar dues solucions d’emmagatzematge**:

- Una per **entorns Linux** utilitzant **LVM (Logical Volume Manager)**.  
- Una per **entorns Windows** utilitzant **Espais d’Emmagatzematge (Storage Spaces)**.

Aquest projecte serà una **prova de concepte**, així que treballarem amb **màquines virtuals** en lloc de servidors reals.

La documentació de cada part (Linux i Windows) es troba en aquesta mateixa carpeta, i aquest README és la portada amb els enllaços als dos documents.

---

## 🐧 Part Linux — LVM amb Zorin OS

En aquesta part s’ha de demostrar el funcionament de LVM utilitzant Zorin OS (o un altre Linux compatible).  
Els punts principals a documentar són:

### ✔️ Requisits
- Crear un **Volume Group (VG)** i un **Logical Volume (LV)** amb dos discos de 10 GB.  
- Formatar-lo i muntar-lo amb configuració persistent a **/etc/fstab**.
- Configurar un **mirall LVM (lvm_mirror)** per tenir alta disponibilitat.
- Afegir dos discos nous de 10 GB:
  - Crear un volum **lvm_dades**, muntar-lo i afegir-hi arxius.
  - Crear un **snapshot (lv_snapshot)** i explicar com restaurar-lo.
- Demostrar com **ampliar un volum** utilitzant l’espai lliure del VG.

📄 **Documentació Linux:**  
➡️ *Enllaç al document de LVM* (afegir quan estigui creat)

---

## 🪟 Part Windows — Espais d’Emmagatzematge (Storage Spaces)

Aquesta part es fa amb Windows 11 i la seva eina d’Espaces d’Emmagatzematge.

### ✔️ Requisits
- Crear un **Storage Pool** amb tres discos de 10 GB.
- Documentar la creació d’Espais d’Emmagatzematge amb:
  - **Mirroring** (utilitzant dos discos).
  - **Parity** (usant els tres discos, explicant eficiència d’espai).
  - **Triple mirroring** (afegint els discos necessaris).
- Mostrar com es visualitza:
  - L’estat dels discos.
  - La salut del pool.
  - Les eines de manteniment i gestió.

📄 **Documentació Windows:**  
➡️ *Enllaç al document d’Espais d’Emmagatzematge* (afegir quan estigui creat)

---

## 📂 Lliurament i organització

- El treball es fa **per grups**, dividits en equip Linux i equip Windows.  
- Cada membre prepara primer el seu **guió personal**, després cada parella realitza la seva demostració.  
- Al final, tot el grup revisa els documents i **cada membre puja la mateixa documentació al seu repositori**.
- A la carpeta `tasca03/` hi ha:
  - Aquest `README.md`
  - `linux_LVM.md`
  - `windows_storage_spaces.md`

La nota és **conjunta**, així que és important coordinar-se bé.  
També haureu de fer una **presentació final al client** amb els resultats obtinguts.

---

## 📘 Recursos (Moodle)
- LVM a Linux  
- Espais d’emmagatzematge a Windows  
*(Afegir els enllaços quan es tinguin)*


