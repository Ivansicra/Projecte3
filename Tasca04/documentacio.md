Durant la instal·lació del servidor he configurat el nom d’usuari, el nom del servidor i la contrasenya.

![Captura 1](img/1.png)

Actualitzo els paquets de la màquina virtual.

![Captura 1](img/2.png)

Configuro el nom i el domini del servidor.

![Captura 1](img/3.png)

Instal·lo OpenLDAP mitjançant la següent comanda

![Captura 1](img/4.png)

Un cop instal·lat s’obrira la següent pantalla, ens demana posar una contrasenya.

![Captura 1](img/5.png)

Comprovo que el servei està funcionant.

![Captura 1](img/6.png)

Comprovo que el directori s’ha creat amb el nom que volia.

![Captura 1](img/7.png)

Si el nom del directori no es el que volia faig la comanda “dpkg-reconfigure slapd”, la qual m’obrira la pantalla a continuació. Primer de tot diem que no volem cancelar la configuració de la BDD.

![Captura 1](img/8.png)

Posem el nom corresponent al directori que volem crear.

![Captura 1](img/12.png)

Poso el nom de la organització.

![Captura 1](img/11.png)

Configuro la contrasenya d'administrador novament: p@ssw0rd.

![Captura 1](img/13.png)

Indica que quan s'elimini el paquet, també s’esborri la BD creada.

![Captura 1](img/14.png)

Comprovo com s’ha modificat la informació de directori.

![Captura 1](img/16.png)

Creo un nou arxiu “.ldif”.

![Captura 1](img/17.png)

dins d’aquest arxiu escric el següent contingut i creo dos nous objectes, 2groups” i “users”.

![Captura 1](img/18.png)

Declaro els dos nous objectes al directori que acabo de crear amb l’ajuda de l’eina “ldapadd”.

![Captura 1](img/19.png)

Mitjançant la comanda “ldapsearch” comprovo que els objectes s’han creat correctament dins del directori.

![Captura 1](img/20.png)

Instalar LDAP account manager amb aquesta comanda:

![Captura 1](img/21.png)

Edito el arxiu netplan i configuro la ip, posaré dhcp en activat per a que crei una ip de forma automatica.

![Captura 1](img/22.png)

Aplico els canvis que he fet en el document de netplan.

![Captura 1](img/23.png)

Comprovo quina ip automatica m’ha creat el sistema mitjançant la comanda “ip a”.

![Captura 1](img/24.png)

Obro “192.168.56.101/lam” premo TAB i obrira una pantalla de control de LDAP Account Manager.

![Captura 1](img/25.png)

configuro la meva contraseña: lam.

![Captura 1](img/26.png)

Un cop dins em trobaré aquesta pantalla de configuració.

![Captura 1](img/27.png)

Dins de la pàgina de configuració anterior cambio el idioma.

![Captura 1](img/28.png)

Configuro l’usuari d’administrador.

![Captura 1](img/29.png)

Vaig a l’apartat de “Acoount types” dins de la pantalla de configuració anterior i cambio el sou dels users i groups.

![Captura 1](img/30.png)

Creo un grup.

![Captura 1](img/31.png)

Creo un usuari

![Captura 1](img/32.png)

Afegeixo un usuari de Unix a l'usuari prèviament creat.

![Captura 1](img/33.png)

Configuro una contrasenya al usuari.

![Captura 1](img/36.png)

Faig click a “save” i guardo l’usuari.

![Captura 1](img/37.png)

Creo la maquina client en Zorin i poso dos adaptadors de xarxa, el NAT i el Host-only.

![Captura 1](img/101.png)

Creo una snapshot de la maquina.

![Captura 1](img/102.png)

Edito la configuració de l’arxiu de Hosts

![Captura 1](img/103.png)

Configuro el ldap amb la comanda: “ sudo apt install libnss-ldap libpam-ldap ldap-utils nscd -y”.

![Captura 1](img/104.png)
![Captura 1](img/105.png)
![Captura 1](img/106.png)
![Captura 1](img/107.png)
![Captura 1](img/108.png)

Comprovo la connexió.

![Captura 1](img/111.png)

Configuro l’arxiu “nsswitch.conf”.

![Captura 1](img/110.png)

Configuro l’arxiu /etc/pam.d/common-password.

![Captura 1](img/112.png)

configuro l’arxiu /etc/pam.d/common-session.

![Captura 1](img/113.png)

Reinicio el servei

![Captura 1](img/115.png)

Configuro l’arxiu /etc/pam.d/gdm-launch-environment.

![Captura 1](img/114.png)
