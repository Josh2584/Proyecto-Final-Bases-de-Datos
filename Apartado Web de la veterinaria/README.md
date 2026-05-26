# Veterinaria Gran Malo — Sistema Web
## Instrucciones de instalación

---

### Archivos del proyecto
```
veterinaria_web/
├── conexion.php      ← Conexión a Oracle (edita tus credenciales aquí)
├── sidebar.php       ← Menú lateral (se incluye en todas las páginas)
├── style.css         ← Estilos de la aplicación
├── index.php         ← Panel principal con métricas
├── mascotas.php      ← Animales disponibles
├── productos.php     ← Catálogo de productos
└── operaciones.php   ← Consultas y cirugías
```

---

### Requisitos

1. **Servidor web con PHP** — recomendado: XAMPP o WAMP
2. **Extensión OCI8 para PHP** — para conectarse a Oracle
3. **Oracle Database** — con el esquema de Veterinaria Gran Malo creado

---

### Paso 1: Activar OCI8 en XAMPP

La extensión `oci8` no viene activada por defecto. Para activarla:

1. Abre el archivo `php.ini` de XAMPP
   - Ruta típica: `C:\xampp\php\php.ini`
2. Busca la línea:
   ```
   ;extension=oci8_12c
   ```
3. Quita el punto y coma (`;`) al inicio para activarla:
   ```
   extension=oci8_12c
   ```
4. Guarda el archivo y reinicia Apache desde el panel de XAMPP

> Si no aparece esa línea, busca `oci8` en el archivo.

---

### Paso 2: Instalar Oracle Instant Client

OCI8 necesita las librerías de Oracle. Descarga **Oracle Instant Client**:
- https://www.oracle.com/database/technologies/instant-client/downloads.html
- Descarga la versión **Basic** para Windows 64-bit
- Extrae la carpeta (ej. `C:\oracle\instantclient_21_12`)
- Agrega esa carpeta al **PATH** del sistema

---

### Paso 3: Configurar la conexión

Edita el archivo `conexion.php` con tus datos:

```php
$host       = 'localhost';      // IP de tu servidor Oracle
$puerto     = '1521';           // Puerto (1521 es el predeterminado)
$sid        = 'XE';             // SID de tu base de datos
$usuario    = 'tu_usuario';     // Tu usuario de Oracle
$contrasena = 'tu_contrasena';  // Tu contraseña
```

---

### Paso 4: Copiar los archivos al servidor

1. Copia la carpeta `veterinaria_web/` a:
   ```
   C:\xampp\htdocs\veterinaria_web\
   ```
2. Abre tu navegador y ve a:
   ```
   http://localhost/veterinaria_web/index.php
   ```

---

### Error conocido en el SQL original

En la tabla `EMPLEADO`, la columna `Salario` está definida como:
```sql
Salario VARCHAR2(10,2)    -- INCORRECTO
```
Debe ser:
```sql
Salario NUMBER(10,2)      -- CORRECTO
```
Corrige esto en tu base de datos si aún no lo has hecho.

---

### Páginas disponibles

| Página | URL | Descripción |
|--------|-----|-------------|
| Inicio | `/index.php` | Métricas generales del sistema |
| Mascotas | `/mascotas.php` | Animales disponibles, con filtros |
| Productos | `/productos.php` | Catálogo de productos e inventario |
| Operaciones | `/operaciones.php` | Consultas y cirugías (con tabs) |
