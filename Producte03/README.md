# P03: Rèplica web – README de la tasca

Aquest document descriu l’objectiu, els requisits i el procés de realització de la tasca **P03: Rèplica web**, emmarcada en l’escenari *“Sobreviure en una empresa IT”* del curs.

---

## 📌 Descripció

L’equip de la consultora ha rebut l’encàrrec de replicar en un entorn local la web corporativa real [davidperalvarez.com](https://davidperalvarez.com/), construïda amb WordPress.  
L’objectiu no és només copiar l’aparença visual, sinó **entendre l’estructura de continguts, la jerarquia d’informació, l’arquitectura SEO i les bones pràctiques** de desenvolupament i manteniment web professional.

Cada alumne treballarà de manera individual, creant una còpia fidel de la web original (pàgines, enllaços, menús, estils i organització interna) utilitzant **WP Local** com a entorn de proves.

---

## 🎯 Objectius específics

- Analitzar una web professional feta amb WordPress per comprendre’n l’estructura i components.
- Reproduir manualment totes les pàgines principals a partir del mapa XML del lloc original.
- Configurar correctament un lloc WordPress local: pàgina d’inici estàtica, menús, enllaços permanents, etc.
- Treballar la coherència visual, la jerarquia de continguts i l’experiència d’usuari (UX).
- Preparar-se per a futurs projectes de creació o manteniment de webs reals per a clients.

---

## 🛠️ Entorn de treball

- **Eina principal:** [WP Local](https://localwp.com/) (instal·lat a l’ordinador de classe)
- **Nom del lloc:** `replica_[nom]`  
  Exemple: `replica_Cristian`
- **Tema/plugins recomanats:**
  - [Kadence Blocks](https://wordpress.org/plugins/kadence-blocks/) – per crear blocs avançats amb Gutenberg.
  - Eines externes d’anàlisi:  
    - [WP Theme Detector](https://www.wpthemedetector.com/) – per identificar tema i plugins.  
    - [Image Color Picker](https://imagecolorpicker.com/ca) – per obtenir colors exactes.  
    - [MyFonts](https://www.myfonts.com/es) – per identificar tipografies.  
    - Sitemap XML de la web original: [https://davidperalvarez.com/page-sitemap.xml](https://davidperalvarez.com/page-sitemap.xml)

---

## 📄 Llistat de pàgines a replicar

1. **Inici**
2. **Sobre mí**
3. **Academia básica**
4. **Mantenimiento para academias online**
5. **Consultoría para academias online**
6. **Proyectos que he realizado**
7. **Descarga**
8. **Contactar**
9. **Política de privacidad**
10. **Política de cookies**
11. **Condiciones de uso**

Totes aquestes pàgines han de ser creades manualment dins del WordPress local, respectant tant com sigui possible:

- Els títols i encapçalaments.
- L’estructura de seccions (textos, imatges, vídeos, llistes).
- L’estil visual (colors, tipografia, disposició).
- La navegació principal (menús i submenús).

> 📝 **Nota sobre continguts:**  
> Es permet utilitzar *Lorem Ipsum* per als paràgrafs llargs, però cal mantenir els títols, subtítols i l’estructura visual original.

---

## 🔧 Configuració del lloc WordPress

Un cop creades totes les pàgines, cal ajustar la configuració general:

1. **Pàgina d’inici estàtica**  
   - Anar a *Configuració > Lectura* i seleccionar “Una pàgina estàtica” → assignar la pàgina *Inici*.

2. **Menú principal**  
   - Crear un menú amb els elements principals i submenús (si n’hi ha) des de *Aparença > Menús*.  
   - Assignar-lo a la ubicació “Menú principal”.

3. **Tema visual**  
   - Provar diferents temes fins a trobar-ne un que s’assembli al disseny original (colors, amplada, tipografia).  
   - Opcional: personalitzar el tema amb CSS addicional o el personalitzador.

4. **Enllaços permanents**  
   - Anar a *Configuració > Enllaços permanents* i triar l’opció *Nom de l’entrada* (`/%postname%/`) per tenir URLs netes.

5. **Paràmetres generals**  
   - Títol del lloc, idioma (català/castellà), zona horària, etc.

---

## ✅ Criteris d’avaluació (per a l’alumne)

| Aspecte                                    | Puntuació |
|--------------------------------------------|-----------|
| Creació completa de totes les pàgines      | 30%       |
| Fidelitat visual / estructura              | 25%       |
| Configuració correcta del menú i inici     | 20%       |
| Ús d’enllaços permanents i configuració    | 10%       |
| Qualitat de la replicació (UX, coherència) | 15%       |
| **Total**                                  | **100%**  |

---

## 📤 Lliurament

Cada alumne haurà de lliurar:

- Un **enllaç a l’exportació del lloc** (fitxer `.zip` o `.sql`) generat amb WP Local, o bé una captura de pantalla del funcionament local.
- Un breu **informe reflexiu** (màxim 1 pàgina) explicant:
  - Què has après analitzant la web original.
  - Quines dificultats has trobat en la replicació.
  - Com has resolt la qüestió del tema visual (tema escollit, personalitzacions).

---

## 📅 Termini

Consulta el calendari del curs per a la data límit de lliurament.

---

## ⚠️ Nota important

Aquesta activitat té una finalitat **exclusivament formativa** i es realitza en un entorn local. No es difondrà cap contingut amb drets d’autor fora de l’àmbit del curs.

---

**Bones pràctiques i … a replicar!** 🚀
