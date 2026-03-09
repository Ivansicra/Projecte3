# T03: Missió Nginx: Migració d'Alt Rendiment i 


## Instalación nginx 

### Primero de todo lo que haremos es parar el servicio apache2 

```bash
systemctl disable apache2
```
![pics](pics/24.png)
#### Como podemos observar el servicio apache2 deshabilitado

### Seguidamente instalaremos el servicio nginx

```bash
apt install nginx -y
```
![pics](pics/25.png)
#### Como podemos comprobar se ha instalado correctamente el servicio nginx

## Personalización de errores

![pics](pics/53.png)
#### Como podemos ver nos sale un error personalizado cuando vamos a un sitio que no existe en la web

## Arhivos de configuración

```bash
cp default academia
cp default projectenexus
```
![pics](pics/44.png)
#### Hemos hecho las siguientes copias porque son las que utilizaremos más adelante

### Configuración de los arhivos projectenexus & academia

```bash
nano academia
```
![pics](pics/45.png)
#### academia

```bash
nano projectenexus
```
![pics](pics/46.png)
#### projectenexus

## Habilitando Server Block

### Es una acción similar a la que se hace en Apache con a2ensite, pero en cambio aquó tendremos que usar directamente la comanda ln para crear el soft link

```bash
ln -s /etc/nginx/sites-available/academia /etc/nginx/sites-enabled/
ln -s /etc/nginx/sites-available/projectenexus /etc/nginx/sites-enabled/
```
![pics](pics/47.png)
#### En nuestro caso nos sale que da error porque ya lo he hecho antes

## Server Blocks

### Evitar problemas de memória
#### Esta es la ruta del archivo

```bash
cd /etc/nginx/nginx.conf
```
# 
```bash
server_names_hash_bucket_size 64;
```
![pics](pics/1.png)
#### Lo que tendremos que hacer es sacarle el hastag o escribir el código que he puesto anteriormente

## Prueba de funcionamiento

### Cliente Zorin

```bash
curl -L https://www.academia.test
```
![pics](pics/8.png)
#### Con esta comanda comprobamos que funciona correctamente

## Personalización de errores

## Creación certificados autoasignados

```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
> -keyout /var/www/projectenexus/private/projectenexus.key \
> -out /var/www/projectenexus/cert/projectenexus.crt

openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
> -keyout /var/www/academia/private/academia.key \
> -out /var/www/academia/cert/academia.crt
```
![pics](pics/10.png)
![pics](pics/11.png)
#### Con esta comanda creamos los certificados

## Convertir sites a HTTPs

```bash
cp academia academia.tls
cp projectenexus projectenexus.tls
```
#### Copiamos los archivos que hemos modificado anteriormente porque así ya tenemos nuestra estructura hecha

### Archivo .tls

```bash
nano academia.tls
nano projectenexus.tls
```
![pics](pics/48.png)
![pics](pics/49.png)
#### Dentro de los archivos haremos la misma configuración que la que se muestra en pantalla

```bash
nginx -t
systemctl restart nginx
```
![pics](pics/7.png)
#### Hacemos esas 2 comandas por separado para comprobar que no está todo correcto

### HTTPs: Proteger la carpeta

```bash
location /private {
        deny all;
        return 403;
}
```
![pics](pics/50.png)
![pics](pics/51.png)

#### Añadimos las siguientes líneas de código  

### Comprobación
![pics](pics/2.png)
![pics](pics/19.png)

### Redirección 

## Si queremos que todas nuestras peticiones vayan a la página https, tendremos que hacer una redirección del site
```bash
return 301 htttps://www.academia.test$request_uri;
return 301 htttps://www.projectenexus.test$request_uri;
```

![pics](pics/20.png)
![pics](pics/21.png)

### Comprobación
![pics](pics/37.png)

## HTTP/2

### El servidor nginx ya soporta directamente HTTP/2, solo hace falta indicar al site seguro que esuche este protocolo

```bash
listen 443 ssl http2;
```
![pics](pics/42.png)
![pics](pics/43.png)

#### Tenemos que añadir la siguiente línea de código en ambos archivos

```bash
systemctl restart nginx
```
#### Recordar hacer esta comanda porque sino NO funcionará

### Comprobación

```bash
curl -I -k --http2 https://www.projectenexus.test
curl -I -k --http2 https://www.academia.test
```
![pics](pics/35.png)
![pics](pics/52.png)

## Aquí finaliza la docuemntación

- [**Readme**](readme.md)
- [**Tornar el projecte**](../README.md)



















