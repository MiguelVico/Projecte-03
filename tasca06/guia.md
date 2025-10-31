# T06: Fonaments del servei DNS - Guia Pràctica

## Introducció
Aquesta guia explica com realitzar una auditoria DNS utilitzant les comandes `dig` i `nslookup`. L'objectiu és diagnosticar problemes de resolució de noms i entendre el funcionament del sistema DNS.

---

## A. Diagnosi Avançada amb `dig`

### Comanda 1: Consulta Bàsica de Registre A
**Comanda executada:** `dig xtec.cat A`

![Consulta A de xtec.cat](/tasca06/img_T06_Fonaments_del_servei_DNS/T06.1.png)

**Anàlisi:**
- **IP de resposta:** 83.247.151.214
- **Valor TTL:** 576 segons
- **Servidor que ha respost:** 127.0.0.53#53 (el servidor DNS local)
- **Temps de consulta:** 38 ms

Aquesta consulta ens mostra la IP associada al domini xtec.cat. El TTL ens indica quant de temps es guardarà aquesta resposta a la memòria cau abans de fer una nova consulta.

---

### Comanda 2: Consulta de Servidors de Noms (NS)
**Comanda executada:** `dig tecnocampus.cat NS`

![Consulta NS de tecnocampus.cat](/tasca06/img_T06_Fonaments_del_servei_DNS/T06.2.png)

**Anàlisi:**
Els servidors de noms autoritatius per a tecnocampus.cat són:
- ns-1071.awsdns-05.org.
- ns-130.awsdns-16.com.
- ns-1689.awsdns-19.co.uk.
- ns-535.awsdns-02.net.

Aquests són els servidors que tenen la informació oficial i actualitzada del domini tecnocampus.cat.

---

### Comanda 3: Consulta Detallada SOA
**Comanda executada:** `dig escolapia.cat SOA`

![Consulta SOA de escolapia.cat](/tasca06/img_T06_Fonaments_del_servei_DNS/T06.3.png)

**Anàlisi:**
- **Correu de l'administrador:** root.dns1.nominalia.com.
- **Número de sèrie:** 1761028965

El registre SOA conté informació important sobre la zona DNS, incloent el contacte de l'administrador i el número de sèrie que s'incrementa cada vegada que es fa un canvi a la zona.

---

### Comanda 4: Consulta de Resolució Inversa
**Comanda executada:** `dig -x 147.83.2.135`

![Resolució inversa de 147.83.2.135](/tasca06/img_T06_Fonaments_del_servei_DNS/T06.4.png)

**Anàlisi:**
S'obtenen múltiples noms de domini associats a aquesta IP:
- upc.edu
- www.upc.es
- upc.cat
- barcelonatech.upc.edu
- i altres...

Això significa que aquesta IP està compartida per diversos serveis de la UPC, una pràctica comuna anomenada "virtual hosting".

---

## B. Comprovació de Resolució amb `nslookup`

### Comanda 1: Consulta Bàsica no Autoritativa
**Comandes executades:**
```
nslookup
set type=A
tecnocampus.cat
```

![Consulta A amb nslookup](/tasca06/img_T06_Fonaments_del_servei_DNS/T06.5.png)

**Anàlisi:**
Indica que la resposta és "no autoritativa" perquè la informació s'ha obtingut des de la memòria cau del servidor DNS local (127.0.0.53) i no directament des dels servidors autoritatius del domini.

---

### Comanda 2: Consultes Autoritatives
**Comandes executades:**
```
nslookup
set type=NS
tecnocampus.cat
server ns-130.awsdns-16.com
set type=A
tecnocampus.cat
```

![Configuració servidor autoritatiu](/tasca06/img_T06_Fonaments_del_servei_DNS/T06.6.png)
![Consulta autoritativa](/tasca06/img_T06_Fonaments_del_servei_DNS/T06.7.png)
![Resultat consulta autoritativa](/tasca06/img_T06_Fonaments_del_servei_DNS/T06.8.png)

**Anàlisi:**
Les diferències observades són:
- **A la comanda 1:** La resposta venia del servidor local i era marcada com "no autoritativa"
- **A la comanda 2:** La resposta ve directament del servidor autoritatiu (ns-130.awsdns-16.com) i és considerada autoritativa

Quan consultem directament als servidors autoritatius, obtenim la informació més actualitzada i fiable del domini.

---

## Conclusions

### Resolució Local
La resolució local funciona mitjançant el servidor DNS configurat localment (127.0.0.53 en aquest cas), que actua com a reenviador i guarda les respostes en memòria cau per millorar el rendiment.

### Aplicacions Pràctiques
Aquestes eines són essencials per:
- Diagnosticar problemes de connectivitat
- Verificar que els dominis s'estan resolent correctament
- Comprovar la configuració DNS dels serveis
- Auditar la seguretat i rendiment dels serveis de noms

### Recomanacions per DigiCore
- Verificar regularment la resolució DNS dels seus dominis crític
- Monitoritzar els temps de resposta DNS
- Configurar TTLs apropiats segons les necessitats de cada servei
- Utilitzar aquestes comandes per diagnosticar ràpidament problemes de connectivitat

---

*Document elaborat per l'equip tècnic d'EverPia - Auditoria DNS per a DigiCore*
