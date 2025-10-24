# 🛡️ T01: Gestor de contrasenyes

## 📋 Descripció
EverPia ha patit un **atac de ciberdelinqüents** i s'ha detectat l'ús de **contrasenyes febles i reutilitzades**.  
La Direcció Tècnica ha decidit que tot el **personal tècnic** ha d'utilitzar un **gestor de contrasenyes** per garantir l'ús de credencials úniques i robustes.

---

## 📁 Contingut de la carpeta
- **informe.md**: Informe tècnic amb comparativa de gestors i justificació de la tria.  
- **guia.md**: Guia d'ús detallada per al personal tècnic basada en l'eina seleccionada.  
- **img/**: Carpeta amb les captures de pantalla utilitzades a la guia.

---

## 🎯 Objectius
- Analitzar els riscos associats a **contrasenyes febles o reutilitzades**.  
- Comparar diferents opcions de **gestors de contrasenyes**.  
- Proporcionar una **guia clara** per a la instal·lació i ús de l'eina triada.

---

## 🔐 Un gestor de contrasenyes permet:
- Crear **contrasenyes úniques i complexes** per a cada compte.  
- **Emmagatzemar-les de manera segura**.  
- Fer **emplenament automàtic i sincronització fiable**, reduint la necessitat de memoritzar-les.

---

## ⚙️ Comparativa Tècnica

| **Característica** | **Bitwarden (Online/Núvol)** | **KeePassX / KeePassXC (Offline)** |
|---------------------|------------------------------|------------------------------------|
| **Sincronització** | Automàtica en núvol, accés des de múltiples dispositius | Manual (arxiu KDBX), necessària sincronització externa si es vol accés multi-dispositiu |
| **Model de seguretat** | Xifratge end-to-end AES-256 | Xifratge AES-256 de l'arxiu local |
| **Accés multi-dispositiu** | Sí, web, app mòbil, extensió navegador | Només amb arxiu KDBX portat a cada dispositiu |
| **Cost / Model freemium** | Gratuït amb opcions Premium (sync avançat, 1GB emmagatzematge) | Totalment gratuït i open-source |
| **Independència del núvol** | Depenent del servei | Totalment offline, no depèn del núvol |
| **Portabilitat** | Limitada si no es disposa d’internet | Molt alta, només cal l’arxiu KDBX |

---

## ✅ Avantatges i Inconvenients

### **Bitwarden (Online)**
**Pros:**
- Sincronització automàtica.  
- Fàcil accés des de qualsevol dispositiu.  
- Còpia de seguretat automàtica.  

**Contres:**
- Dependència del núvol.  
- Risc si el servei es compromet.  

---

### **KeePassX / KeePassXC (Offline)**
**Pros:**
- Control total de l’arxiu.  
- Independència del núvol.  
- Open-source.  

**Contres:**
- Més complex de sincronitzar entre dispositius.  
- Risc de pèrdua si no es fa **backup**.  

---

## 🧭 Recomanació

Es recomana **Bitwarden** per al personal tècnic, ja que:

- Permet un **ús senzill i segur** des de múltiples dispositius.  
- **Minimitza errors humans** en la gestió de contrasenyes.  
- La **sincronització automàtica** garanteix la continuïtat del negoci i còpies de seguretat sense complexitat addicional.
