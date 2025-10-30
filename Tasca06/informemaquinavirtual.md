## 1. Configuro dos ports de xarxa, un principal en “NAT”, i un secundari en “Pont”.
![Captura 1](img/1.png)


## 2. Activo el port ethernet “Pont”.
![Captura 2](img/2.png)


## 3. Configuro IP i màscara.
![Captura 3](img/3.png)


## 4. Comprovo la connexió.
![Captura 4](img/4.png)


## 5. Faig una consulta amb la comanda “dig”:

5.1. Consulta bàsica de registre: “A”
![Captura 5](img/5.png)


5.2. Consulta de servidor de noms: “NS”
![Captura 6](img/6.png)


5.3. Consulta detallada: “SOA”
![Captura 7](img/7.png)


5.4. Consulta resolució inversa.
![Captura 8](img/8.png)


## 6. Consulta no autoritativa.
![Captura 9](img/9.png)


## 7. Consulta autoritativa.
![Captura 10](img/9.png)

La Principal diferencia entre una consulta no autoritativa i una consulta autoritativa, es que l’apartat de resposta “Non-authoritative answer” no apareix quan la consulta es autoritativa.
