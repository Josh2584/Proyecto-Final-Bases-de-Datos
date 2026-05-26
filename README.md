Proyecto Final de Bases de Datos

Se necesita XAMPP, Oracle Instant Client y Oracle

En el caso de XAMPP, basta con marcar Apache y PHP al momento de istalarlo.

En el caso de Oracle Instant Client, Se necesita agregar la carpeta extraida al PATH.

Al tener estos 2 pasos anteriores, buscamos la carpeta php de xampp y selecionamos el archivo php.ini,
buscamos ; extension=oci8_19c, eliminamos ; y guardamos el archivo.

Creamos una carpeta llamada Veterinaria en xampp\htdocs y agrega todos los archivos del apartado web.

Revisa el archivo de conexión en el se encuentra el nombre y contraseña que le debes de dar a la base de datos para conectarla, 
en caso de tener otro nombre o contraseña modificalo.

Abre la aplicación de XAMPP y activa apache.

Ahora acceda a la siguiente URL: http://localhost/veterinaria/index.php

Si todo esta bien debería de aparecerte un menú.


Páginas disponibles

Inicio.
URL: /index.php	
Descripción: Métricas generales del sistema

Mascotas.
URL: /mascotas.php
Descripción: Animales disponibles, con filtros

Productos.
URL: /productos.php
Descripción: Catálogo de productos e inventario

Operaciones.
URL: /operaciones.php
Descripción: Consultas y cirugías (con tabs)
