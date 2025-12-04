# 
# Configuración del sistema de IsardVDI:
-El primer paso que hemos de realizar es poner nuestras credenciales en IsardVDI y luego elegir una maquina virtual, configurar-la e iniciar-la.
-Despues de entrar toca abrir la terminal y configurar la maquina para poder empezar la instalación.

# Instalación de LAMP stack en Ubuntu 24.04

La palabra LAMP viene de:

-Linux (el sistema operativo)

-Apache (el programa que muestra páginas web)

-MySQL (el programa que guarda datos)

-PHP (el lenguaje que usan muchas webs)

Vamos a instalar todo paso a paso.

## 1. Actualiza el sistema
sudo apt update && sudo apt upgrade -y

## 2. Instal·la Apache
sudo apt install apache2 -y

### Activa e inicia el servicio:
sudo systemctl enable apache2
sudo systemctl start apache2

### Verifica el estado:
sudo systemctl status apache2
Visita http://localhost per veure la pàgina per defecte d’Apache.

## 3. Instal·la MySQL
Ubuntu 24.04 ja inclou el paquet mysql-server als repositoris oficials (versió 8.0 o superior):
sudo apt install mysql-server mysql-client -y

### Inicia i habilita el servei:
sudo systemctl enable mysql
sudo systemctl start mysql

### Configura de MySQL:
Accés a la consola de MySQL
sudo mysql

### Creació de la base de dades
CREATE DATABASE bbdd;

### Creació de l’usuari local
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
GRANT ALL PRIVILEGES ON bbdd.* TO 'usuario'@'localhost';
FLUSH PRIVILEGES;
EXIT;

Nota: Aquest usuari només pot connectar-se des del servidor local (localhost), cosa que és suficient si l’aplicació web i la base de dades estan al mateix servidor.

## 4. Instal·la PHP i extensions comunes
Ubuntu 24.04 inclou PHP 8.3 als repositoris estàndard:
sudo apt install php libapache2-mod-php php-mysql php-curl php-gd php-mbstring php-xml php-zip php-json php-cli -y

### Reinicia Apache per carregar PHP:
sudo systemctl restart apache2

### Verifica la versió de PHP:
php -v

### Crea un fitxer de prova:
echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
Visita http://localhost/info.php per veure la informació de PHP.


## 🔒 Mesura de seguretat: Un cop hagis verificat que funciona, elimina el fitxer:
sudo rm /var/www/html/info.php

#### Verificació final

La pila LAMP ara hauria d’estar operativa amb:
Apache servint pàgines web.
MySQL preparat per emmagatzemar dades.
PHP processant scripts.

# Configuració de VirtualHost amb apache2
Apache permite tener varias webs en el mismo ordenador.

Cada una funciona como si fuera una web diferente, con su nombre propio.
A eso se le llama VirtualHost.

## Con esto podrás entrar a tu web escribiendo algo como:
👉 www.domini.local

Vamos paso a paso.

## 1. Crear la carpeta donde irá tu web

### Todas las webs que uses las vamos a guardar dentro de:
/var/www/

### Creamos una carpeta para nuestra web llamada domini.local:

sudo mkdir -p /var/www/domini.local

Piensa en esta carpeta como “la mochila” donde estarán tus archivos de la web.
