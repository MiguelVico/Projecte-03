# T04: Serveis de directori. LDAP - Guia d'Instal·lació i Configuració

## Introducció
Aquesta guia explica pas a pas com instal·lar i configurar un servidor OpenLDAP per centralitzar l'autenticació d'usuaris a Innovatech.

## 1. Preparació de la Màquina Virtual

### Configuració inicial de la VM

![Configuració de la màquina virtual](/tasca4/img_T04/captura1.png)

Estem creant una nova màquina virtual amb VirtualBox. Configurem la memòria (4096 MB), processadors (2) i disc dur necessari per al servidor.

### Configuració de xarxa

![Configuració de xarxa](/tasca4/img_T04/captura2.png)

Configurem l'adaptador de xarxa en mode "Adaptador de només l'amfitrió" per crear una xarxa privada entre host i VM.

### Configuració del sistema

![Configuració del sistema](/tasca4/img_T04/captura3.png)

Configurem els dispositius del sistema: arrencada, emmagatzematge, xarxa i ports. Tot preparat per instal·lar el sistema.

### Configuració del mirror d'Ubuntu

![Configuració del mirror](/tasca4/img_T04/captura4.png)

Establim el mirror d'Ubuntu `http://cs.archive.ubuntu.com/ubuntu/` per la instal·lació del sistema operatiu.

### Configuració de xarxa (alternativa)

![Configuració de xarxa alternativa](/tasca4/img_T04/captura5.png)

Una altra vista de la configuració de xarxa mostrant opcions DHCP i configuracions de connexió.

## 2. Configuració inicial del servidor

### Configuració del fitxer hosts

![Edició del fitxer hosts](/tasca4/img_T04/captura6.png)

Editant el fitxer `/etc/hosts` amb nano per afegir `server.innovatech26.test` i assegurar la resolució correcta del nom.

### Configuració del hostname

![Comanda hostnamectl](/tasca4/img_T04/captura7.png)

Executant `sudo hostnamectl set-hostname server` per canviar el nom del servidor a "server".

### Verificació del hostname

![Verificació del hostname](/tasca4/img_T04/captura8.png)

Verificant amb `hostname -f` i `hostname` que els canvis s'han aplicat correctament.

## 3. Instal·lació d'OpenLDAP

### Instal·lació dels paquets

![Instal·lació d'OpenLDAP](/tasca4/img_T04/captura9.png)

Executant `sudo apt install slapd ldap-utils -y` per instal·lar el servidor OpenLDAP i les utilitats.

### Procés d'instal·lació detallat

![Procés d'instal·lació](/tasca4/img_T04/captura11.png)

El procés d'instal·lació mostra la creació de l'usuari openldap i la configuració inicial del servei.

### Configuració de contrasenya d'administrador

![Contrasenya d'administrador](/tasca4/img_T04/captura18.png)

Introduint la contrasenya per a l'administrador del directori LDAP.

### Confirmació de contrasenya

![Confirmació de contrasenya](/tasca4/img_T04/captura10.png)

Confirmant la contrasenya de l'administrador per verificar que no hi ha errors.

### Configuració de l'organització

![Configuració de l'organització](/tasca4/img_T04/captura17.png)

Establim el nom de l'organització com a `Innovatech26.test` per al DN base del directori.

### Gestió de bases de dades existents

![Gestió de bases de dades antigues](/tasca4/img_T04/captura20.png)

El sistema pregunta si volem moure les bases de dades antigues abans de crear-ne una de nova.

### Configuració de l'esborrat de la base de dades

![Configuració de l'esborrat](/tasca4/img_T04/captura19.png)

Triant si volem que s'esborri la base de dades quan es purgui el paquet slapd.

### Omissió de la configuració inicial

Decidint si volem ometre la configuració del servidor OpenLDAP (triem No).

### Reconfiguració del servei

![Reconfiguració de slapd](/tasca4/img_T04/captura15.png)

Executant `sudo dpkg-reconfigure slapd` per reconfigurar el servei si és necessari.

## 4. Verificació del servei

### Comprovació de l'estat del servei

![Estat del servei slapd](/tasca4/img_T04/captura12.png)

Verificant amb `systemctl status slapd` que el servei està actiu i funcionant correctament.

### Comprovació de la base de dades

![Contingut de la base de dades](/tasca4/img_T04/captura13.png)

Executant `sudo slapcat` per veure el contingut de la base de dades LDAP i verificar la instal·lació.

### Sortida de la base de dades

![Sortida de slapcat](/tasca4/img_T04/captura14.png)

La sortida completa de `slapcat` mostrant l'entrada base `dc=innovatech26,dc=test` i totes les seves propietats.

## 5. Verificació del servei LDAP

### Comprovació de la base de dades LDAP

![Verificació amb slapcat](/tasca4/img_T04/captura21.png)

Executant `sudo slapcat` per veure el contingut de la base de dades LDAP i confirmar que la instal·lació és correcta.

## 6. Creació d'Unitats Organitzatives

### Creació del fitxer LDIF

![Edició del fitxer LDIF](/tasca4/img_T04/captura25.png)

Creant el fitxer `OU_users.ldif` amb nano per definir la Unitat Organitzativa "Usuaris".

### Contingut del fitxer LDIF

![Contingut del fitxer LDIF](/tasca4/img_T04/captura22.png)

El fitxer LDIF conté la definició de la OU amb `ou=Usuaris` i les objectClass necessàries.

### Addició de la OU al LDAP

![Addició de la OU](/tasca4/img_T04/captura23.png)

Executant `ldapadd` per afegir la Unitat Organitzativa al directori LDAP.

### Confirmació de l'addició

![Confirmació de l'addició](/tasca4/img_T04/captura26.png)

El sistema confirma que s'ha afegit correctament la nova entrada "ou=Usuaris,dc=innovatech26,dc=test".

### Verificació de la nova OU

![Verificació amb slapcat](/tasca4/img_T04/captura27.png)

Executant `sudo slapcat` de nou per verificar que la OU "Usuaris" s'ha afegit correctament al directori.

### Configuració de grups locals

![Configuració de grups](/tasca4/img_T04/captura24.png)

Afegint l'usuari actual al grup "usuaris" amb `sudo usermod -aG usuaris $USER`.

## 7. Instal·lació de LDAP Account Manager

### Instal·lació del paquet

![Instal·lació LAM](/tasca4/img_T04/captura28.png)

Instal·lant `ldap-account-manager` i totes les seves dependències, incloent Apache2 i PHP.

### Verificació d'Apache

![Estat d'Apache](/tasca4/img_T04/captura29.png)

Comprovant que Apache2 està actiu i funcionant correctament amb `systemctl status apache2`.

## 8. Configuració de LDAP Account Manager

### Menú principal de LAM

![Menú LAM](/tasca4/img_T04/captura31.png)

Pantalla principal de LDAP Account Manager amb opcions per editar ajustos generals i perfils del servidor.

### Configuració de contrasenya del perfil

![Contrasenya del perfil](/tasca4/img_T04/captura32.png)

Introduint la contrasenya per accedir a la configuració del servidor LAM.

### Configuració d'idioma i zona horària

![Configuració d'idioma](/tasca4/img_T04/captura34.png)

Establint l'idioma per defecte a Español (España) i la zona horària a Europe/Madrid.

### Configuració del lamdaemon

![Preferències lamdaemon](/tasca4/img_T04/captura35.png)

Configurant les preferències del lamdaemon amb opcions de servidor, scripts externs i permisos.

### Configuració de seguretat

![Preferències de seguretat](/tasca4/img_T04/captura36.png)

Establint polítiques de contrasenyes i opcions d'autenticació de 2 factors.

### Configuració de tipus de comptes

![Tipus de comptes](/tasca4/img_T04/captura37.png)

Configurant els sufijos LDAP per a usuaris i grups dins del domini innovatech26.test.

### Creació de sufijos LDAP

![Creació de sufijos](/tasca4/img_T04/captura38.png)

LAM detecta que els sufijos no existeixen i ofereix crear-los automàticament.

### Creació de grups Unix

![Creació de grup Unix](/tasca4/img_T04/captura39.png)

Formulari per crear un nou grup Unix amb nom del grup, número GID i descripció.

### Configuració de grup d'administradors

![Grup d'administradors](/tasca4/img_T04/captura40.png)

Creant el grup "manage" amb els seus paràmetres i opció per editar membres.

## 9. Creació de Grups i Usuaris amb LAM

### Llista de grups creats

![Llista de grups](/tasca4/img_T04/captura41.png)

Pantalla principal de LAM mostrant els grups creats: "manager" amb GID 10001 i "tech" amb GID 10000.

### Interfície principal de LAM

![Interfície LAM](/tasca4/img_T04/captura42.png)

Vista general de LDAP Account Manager amb les pestanyes d'Usuaris i Grups.

### Llista d'usuaris buida

![Llista d'usuaris buida](/tasca4/img_T04/captura43.png)

Pantalla d'usuaris mostrant que encara no hi ha cap usuari creat al directori.

### Formulari de nou usuari

![Formulari nou usuari](/tasca4/img_T04/captura44.png)

Començant a crear un nou usuari amb les dades personals: nom, cognom i descripció.

### Configuració d'usuari Tech

![Usuari Tech](/tasca4/img_T04/captura45.png)

Creant l'usuari "tech26" amb UID 10000, grup primari "tech" i directori home /home/tech26.

### Configuració de contrasenya

![Contrasenya usuari](/tasca4/img_T04/captura46.png)

Establint la contrasenya per a l'usuari "tech26" amb opció de forçar canvi de contrasenya.

### Llista amb usuari Tech

![Llista amb Tech](/tasca4/img_T04/captura47.png)

LAM mostra ara l'usuari "tech26" creat correctament amb totes les seves dades.

### Creació d'usuari Manager

![Usuari Manager](/tasca4/img_T04/captura48.png)

Creant un segon usuari "manager" amb les seves dades personals i adreça.

### Configuració completa Manager

![Configuració Manager](/tasca4/img_T04/captura49.png)

Formulari complet per a l'usuari "manager" amb UID 10001 i grup primari "manager".

### Contrasenya per Manager

![Contrasenya Manager](/tasca4/img_T04/captura50.png)

Establint la contrasenya per a l'usuari "manager".

### Llista final d'usuaris

![Llista final usuaris](/tasca4/img_T04/captura51.png)

LAM mostra els dos usuaris creats: "tech26" i "manager26" amb els seus respectius UIDs i GIDs.

## 10. Configuració del Client LDAP

### Configuració de la màquina client

![Configuració client](/tasca4/img_T04/captura52.png)

Creant una nova màquina virtual client amb configuració de xarxa NAT per connectar-se al servidor.

### Actualització del client

![Actualització client](/tasca4/img_T04/captura53.png)

Executant `sudo apt update && sudo apt upgrade -y` per actualitzar el sistema del client.

### Configuració del hosts del client

![Hosts client](/tasca4/img_T04/captura54.png)

Editant el fitxer `/etc/hosts` per afegir les entrades del servidor: `10.0.2.15 server.innovatech26.test`.

### Test de connexió al servidor

![Ping al servidor](/tasca4/img_T04/captura56.png)

Executant `ping 10.0.2.5` per verificar la connexió de xarxa entre client i servidor.

### Resolució DNS del servidor

![Dig servidor](/tasca4/img_T04/captura57.png)

Verificant la resolució de noms amb `dig server.innovatech26.test` que retorna correctament la IP 10.0.2.5.

## 11. Configuració del Client LDAP

### Configuració URI LDAP

![URI LDAP](/tasca4/img_T04/captura58.png)

Configurant la URI del servidor LDAP: `ldap://server.innovatech26.test` per a la connexió del client.

### Configuració base DN

![Base DN](/tasca4/img_T04/captura59.png)

Establint el DN base de cerca: `dc=innovatech26,dc=test` per a les consultes LDAP.

### Versió de protocol LDAP

![Versió LDAP](/tasca4/img_T04/captura60.png)

Seleccionant la versió del protocol LDAP a utilitzar (versió 3, la més recent i estable).

## 12. Configuració de l'Autenticació LDAP al Client

### Instal·lació de paquets LDAP al client

![Instal·lació paquets client](/tasca4/img_T04/captura65.png)

Instal·lant `ldap-utils`, `nscd`, `libpam-ldap`, `libnss-ldap` i `ldap-auth-client` per configurar l'autenticació LDAP.

### Configuració de la base de dades local

![Configuració base local](/tasca4/img_T04/captura61.png)

Triant no fer l'administrador de la base de dades local, ja que utilitzarem LDAP.

### Requeriment d'inici de sessió LDAP

![Requeriment login LDAP](/tasca4/img_T04/captura62.png)

Confirmant que la base de dades LDAP no requereix login addicional per a les consultes.

### Configuració del compte root LDAP

![Compte root LDAP](/tasca4/img_T04/captura63.png)

Establint `cn=admin,dc=innovatech26,dc=test` com a compte amb privilegis per a canvis de contrasenya.

### Contrasenya del compte admin

![Contrasenya admin](/tasca4/img_T04/captura64.png)

Introduint la contrasenya de l'administrador LDAP que s'emmagatzemarà a /etc/ldap.secret.

## 13. Verificació de la Connexió LDAP

### Consulta LDAP amb autenticació

![Consulta LDAP autenticada](/tasca4/img_T04/captura66.png)

Executant `ldapsearch` amb credencials per veure totes les entrades del directori LDAP.

### Consulta LDAP anònima

![Consulta LDAP anònima](/tasca4/img_T04/captura72.png)

Verificant l'accés anònim al directori amb una consulta que mostra totes les OUs, grups i usuaris.

### Configuració del fitxer nsswitch.conf

![Edició nsswitch.conf](/tasca4/img_T04/captura67.png)

Obrint el fitxer `/etc/nsswitch.conf` per configurar les fonts d'informació del sistema.

### Configuració de nsswitch.conf

![Configuració nsswitch](/tasca4/img_T04/captura68.png)

Afegint `ldap` a les línies de `passwd`, `group` i `shadow` per utilitzar LDAP com a font d'usuaris.

## 14. Configuració de PAM

### Configuració de common-password

![Common-password PAM](/tasca4/img_T04/captura69.png)

Configurant els mòduls PAM per a la gestió de contrasenyes, incloent suport per LDAP.

### Configuració de common-session

![Common-session PAM](/tasca4/img_T04/captura70.png)

Afegint `pam_ldap.so` i `pam_mkhomedir.so` per crear directoris home automàticament.

### Configuració de GDM

![Configuració GDM](/tasca4/img_T04/captura74.png)

Modificant `/etc/pam.d/gdm-launch-environment` per permetre l'autenticació LDAP al gestor de pantalla.

## 15. Verificació Final

### Reinici del servei nscd

![Reinici nscd](/tasca4/img_T04/captura71.png)

Reiniciant el servei Name Service Cache Daemon i verificant el seu estat.

### Verificació amb getent

![Verificació getent](/tasca4/img_T04/captura73.png)

Comprovant amb `getent passwd` que els usuaris LDAP (tech26 i manager26) apareixen al sistema.

## 16. Prova d'Accés

### Login de tech26

![Login tech26](/tasca4/img_T04/captura75.png)

Pantalla d'inici de sessió de Zorin OS amb l'usuari `tech26` introduït.

### Contrasenya de tech26

![Contrasenya tech26](/tasca4/img_T04/captura76.png)

Introduint la contrasenya per a l'usuari `tech26`.

### Escriptori de tech26

![Escriptori tech26](/tasca4/img_T04/captura77.png)

Escriptori de l'usuari `tech26` després de l'inici de sessió exitós amb LDAP.

### Login de manager26

![Login manager26](/tasca4/img_T04/captura78.png)

Pantalla d'inici de sessió amb l'usuari `manager26`.

### Contrasenya de manager26

![Contrasenya manager26](/tasca4/img_T04/captura79.png)

Introduint la contrasenya per a l'usuari `manager26`.

### Escriptori de manager26

![Escriptori manager26](/tasca4/img_T04/captura80.png)

Escriptori de l'usuari `manager26` després de l'inici de sessió exitós amb LDAP.
