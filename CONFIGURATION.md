# 📂 Guía de demostración y administración de Nextcloud

Esta guía documenta cómo usar y administrar un servidor Nextcloud: subir archivos, crear usuarios, asignar permisos y acceder desde cualquier equipo de la red.

## 1️⃣ Demostración del funcionamiento
### 1.1 Subir archivos

### Accede a tu cuenta de Nextcloud.

### Haz clic en “Subir archivo” o arrastra un documento o imagen al navegador.
![Text alternatiu](foto.png)

<img width="815" height="353" alt="unnamed" src="https://github.com/user-attachments/assets/de76a4de-11aa-4b85-b7f0-2cf260a170ee" />

### Verifica que el archivo aparece correctamente en la lista de archivos.
<img width="1512" height="492" alt="image" src="https://github.com/user-attachments/assets/efea2121-cb98-4185-bfbd-5f354a4fcc89" />

### 1.2 Crear carpetas

Haz clic en “Nueva carpeta” dentro de tu espacio de usuario.
<img width="1177" height="755" alt="image" src="https://github.com/user-attachments/assets/45c3fb04-5220-409e-8be3-04c0292e6b6b" />

Crea una estructura básica, por ejemplo:

Documentos

Imágenes

Compartidos

<img width="1203" height="488" alt="image" src="https://github.com/user-attachments/assets/dbba5f21-7e05-4c9f-bcec-d85536d1e11e" />

### 1.3 Compartir contenidos

Selecciona un archivo o carpeta y haz clic en “Compartir”.

Puedes generar un enlace público o compartir directamente con otro usuario de Nextcloud.

Configura opciones como contraseña o fecha de caducidad si es necesario.
<img width="1851" height="546" alt="image" src="https://github.com/user-attachments/assets/81f04a99-8203-41dc-b58f-8f83afbada3c" />

## 2️⃣ Creación de usuarios
### Crear tres usuarios

Accede a la interfaz de administración de Nextcloud.
<img width="1160" height="728" alt="image" src="https://github.com/user-attachments/assets/77de0751-d3e5-4294-8b25-b3e7413341fa" />

Crea tres usuarios:

Administrador → control total.

Editor → puede modificar archivos y carpetas.

Visualizador → solo puede ver archivos.
<img width="1855" height="530" alt="image" src="https://github.com/user-attachments/assets/5f357be6-c8c3-4b9e-a277-a4e485cfeecd" />

## 3️⃣ Asignación de roles y permisos
### Configurar permisos por rol

Administra los permisos desde la interfaz de Nextcloud:

Administrador: todo acceso.

Editor: puede añadir, editar y borrar archivos.

Visualizador: solo lectura.

<img width="1846" height="420" alt="image" src="https://github.com/user-attachments/assets/cb1833ff-3d7e-48dd-aa2a-341ceee604a5" />

### Al entrar en la carpeta con una cuenta diferente la experiencia cambia gracias a los permisos.
<img width="1853" height="761" alt="image" src="https://github.com/user-attachments/assets/159eca26-ec75-4cdc-8568-c1182ddd39f5" />


## 4️⃣ Administración de archivos
### 4.1 Organización de carpetas y archivos

Crea una jerarquía lógica dentro del Nextcloud:

-Documentos Personales

-Carpeta

-Recursos

<img width="1851" height="543" alt="image" src="https://github.com/user-attachments/assets/5f59a520-1f9e-4c3b-abca-489eb4bbff2a" />
<img width="1847" height="737" alt="image" src="https://github.com/user-attachments/assets/6d01f61a-b7f3-41f1-9295-0315cfdd44db" />
<img width="1845" height="796" alt="image" src="https://github.com/user-attachments/assets/46456153-07b2-4cfb-9bc3-a7daab855fd7" />


## 5️⃣ Acceso desde otra máquina de la red
Nextcloud permite que cada usuario pueda montar el almacenamiento de otro usuario como si fuera una carpeta compartida, siempre que ambos lo permitan y tengan las credenciales necesarias. Esto se hace mediante la app External Storage Support (“Almacenamiento externo”).

🔧 1. Activar la app de Almacenamiento Externo (si aún no lo está)

Esto lo debe hacer un administrador:

Entra con la cuenta de administrador en Nextcloud.

Ve a Ajustes → Aplicaciones.

Busca External Storage Support o Almacenamiento externo.

Actívala.

📁 2. Acceder a la configuración de Almacenamiento Externo como usuario

Cada usuario puede añadir accesos externos:

Inicia sesión en tu cuenta de Nextcloud.

En la esquina superior derecha, entra en Ajustes.

Busca la sección Almacenamiento externo o External storage.

🔐 3. Agregar la cuenta de tu compañero

Ahora podrás configurar el acceso al almacenamiento de otro usuario:

Haz clic en “Agregar almacenamiento”.

En la columna Tipo de almacenamiento, selecciona "Nextcloud".

Rellena los campos:

URL: la dirección del servidor (por ejemplo: http://IP-de-la-máquina/nextcloud).

Usuario: nombre de usuario de tu compañero.

Contraseña: la contraseña que él te haya dado.

Nombre de la carpeta local: cómo quieres que aparezca en tu Nextcloud (ej.: “Carpeta de María”).

Marca la casilla de estado (el punto verde indica que funciona correctamente).

📂 4. Usar los archivos de tus compañeros

Una vez configurado correctamente:

Aparecerá una nueva carpeta en tu Vista de Archivos.

Podrás navegar, leer o modificar (según permisos) todos los archivos del usuario remoto.

Todo se comporta como una carpeta normal de Nextcloud, pero sincronizada con la cuenta de tu compañero.
