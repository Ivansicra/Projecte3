# Instal·lació i configuració del servidor amb OpenLDAP

## Configuració inicial

Durant la instal·lació del servidor he configurat el **nom d’usuari**, el **nom del servidor** i la **contrasenya**.

![Captura 1](img/1.png)

Actualitzo els paquets de la màquina virtual.

![Captura 1](img/2.png)

Configuro el **nom** i el **domini** del servidor.

![Captura 1](img/3.png)

---

## Instal·lació d’OpenLDAP

Instal·lo **OpenLDAP** mitjançant la següent comanda.

![Captura 1](img/4.png)

Un cop instal·lat, s’obrirà la següent pantalla i ens demanarà posar una **contrasenya**.

![Captura 1](img/5.png)

Comprovo que el **servei està funcionant**.

![Captura 1](img/6.png)

Comprovo que el **directori s’ha creat** amb el nom que volia.

![Captura 1](img/7.png)

Si el nom del directori no és el correcte, faig servir la comanda:

```bash
dpkg-reconfigure slapd
```

![Captura 1](img/8.png)

Aquesta comanda obrirà una pantalla de configuració.  

![Captura 1](img/11.png)

Primer de tot diem que **no volem cancel·lar la configuració de la BDD**.

![Captura 1](img/12.png)

Posem el **nom corresponent al directori** que volem crear.

![Captura 1](img/13.png)

Poso el **nom de l’organització**.

![Captura 1](img/14.png)

Configuro la **contrasenya d’administrador novament**:  
`p@ssw0rd`

![Captura 1](img/15.png)

Indico que quan s’elimini el paquet, també s’esborri la BD creada.

![Captura 1](img/16.png)

Comprovo com s’ha modificat la informació del directori.

![Captura 1](img/17.png)

---

## Creació de fitxer `.ldif`

Creo un nou arxiu `.ldif`.

![Captura 1](img/18.png)

Dins d’aquest arxiu escric el següent contingut i creo dos nous objectes:  
**groups** i **users**.

![Captura 1](img/19.png)

Declaro els dos nous objectes al directori amb l’ajuda de l’eina **ldapadd**.

![Captura 1](img/20.png)

Mitjançant la comanda següent comprovo que els objectes s’han creat correctament dins del directori:

```bash
ldapsearch
```

![Captura 1](img/21.png)

---

## Instal·lació de LDAP Account Manager

Instal·lo **LDAP Account Manager** amb aquesta comanda.

![Captura 1](img/22.png)

---

## Configuració de la xarxa (Netplan)

Edito l’arxiu **Netplan** i configuro la IP, posant **DHCP** activat perquè creï una IP automàticament.

![Captura 1](img/23.png)

Aplico els canvis que he fet al document de Netplan.

![Captura 1](img/24.png)

Comprovo quina IP automàtica ha creat el sistema amb la comanda:

```bash
ip a
```

![Captura 1](img/25.png)

---

## Accés a LDAP Account Manager

Obro el navegador i accedeixo a:

```
192.168.56.101/lam
```

![Captura 1](img/26.png)

Premo **TAB** i s’obrirà la pantalla de control de **LDAP Account Manager**.

![Captura 1](img/27.png)

Configuro la meva contrasenya:  
`lam`

![Captura 1](img/28.png)

Un cop dins, em trobaré la pantalla de **configuració**.

![Captura 1](img/29.png)


---

## Configuració inicial a LDAP Account Manager

Dins de la pàgina de configuració:

- Canvio l’**idioma**.

![Captura 1](img/30.png)

- Configuro l’**usuari d’administrador**.

![Captura 1](img/31.png)

- A l’apartat **Account types**, canvio el *sou* dels **users** i **groups**.

![Captura 1](img/31.png)

---

## Creació d’usuaris i grups

Creo un **grup**.

![Captura 1](img/32.png)

Creo un **usuari**.

![Captura 1](img/33.png)

Afegeixo un **usuari de Unix** a l’usuari prèviament creat.

![Captura 1](img/34.png)

Configuro una **contrasenya** per a l’usuari.

![Captura 1](img/35.png)

Finalment, faig clic a **Save** i guardo l’usuari.

![Captura 1](img/35.png)


