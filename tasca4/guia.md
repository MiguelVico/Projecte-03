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
![Omissió de configuració](/tasca4/img_T04/captura16.png)
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
