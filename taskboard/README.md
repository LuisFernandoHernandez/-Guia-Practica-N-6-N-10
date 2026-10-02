# Taskboard

Aplicación web desarrollada con **Laravel 13**, PHP y Vite.

## Requisitos

Antes de ejecutar el proyecto, instala:

- PHP **8.3 o superior**
- Composer
- Node.js y npm
- Git (opcional, pero recomendado para trabajar con GitHub)

## Instalación

### 1. Clonar o descargar el proyecto

Si lo estás utilizando desde GitHub:

```bash
git clone URL_DEL_REPOSITORIO
cd taskboard
```

### 2. Instalar las dependencias de PHP

La carpeta `vendor` **no está incluida en el repositorio** porque contiene las dependencias instaladas por Composer y puede ocupar mucho espacio.

Desde la carpeta principal del proyecto ejecuta:

```bash
composer install
```

Esto volverá a crear automáticamente:

```text
vendor/
```

a partir de `composer.json` y `composer.lock`.

### 3. Crear el archivo `.env`

El archivo `.env` tampoco se incluye en GitHub porque puede contener configuraciones y datos sensibles.

Copia `.env.example` y crea `.env`.

En Windows:

```bash
copy .env.example .env
```

En macOS/Linux:

```bash
cp .env.example .env
```

Después genera la clave de Laravel:

```bash
php artisan key:generate
```

### 4. Configuración de la base de datos

Este proyecto utiliza SQLite.

La base de datos se encuentra en:

```text
database/database.sqlite
```

Si necesitas crear una base de datos nueva, puedes ejecutar:

```bash
php artisan migrate
```

Si el proyecto necesita los datos iniciales de los seeders:

```bash
php artisan db:seed
```

> Si el archivo `database/database.sqlite` incluido en el proyecto contiene datos de demostración que quieres conservar, no lo elimines.

### 5. Instalar las dependencias de JavaScript

La carpeta `node_modules` tampoco debe subirse a GitHub.

Ejecuta:

```bash
npm install
```

Esto instalará nuevamente las dependencias definidas en `package.json`.

### 6. Compilar los recursos

Para generar los archivos de frontend:

```bash
npm run build
```

Durante el desarrollo también puedes utilizar:

```bash
npm run dev
```

### 7. Ejecutar Laravel

Inicia el servidor:

```bash
php artisan serve
```

Después abre:

```text
http://127.0.0.1:8000
```

## Instalación rápida

Después de clonar el proyecto, los comandos principales son:

```bash
composer install
copy .env.example .env
php artisan key:generate
npm install
npm run build
php artisan serve
```

Si estás utilizando macOS o Linux, sustituye:

```bash
copy .env.example .env
```

por:

```bash
cp .env.example .env
```

## ¿Por qué no se incluyen algunas carpetas?

### `vendor/`

No se incluye porque Composer puede reconstruirla mediante:

```bash
composer install
```

La carpeta puede ocupar bastante espacio y no es necesario almacenarla en GitHub.

### `.env`

No se incluye porque puede contener claves, contraseñas, credenciales y configuraciones específicas del equipo.

Cada desarrollador debe crear su propio `.env` a partir de `.env.example`.

### `node_modules/`

No se incluye porque npm puede reconstruirla mediante:

```bash
npm install
```

### Archivos generados de `storage/`

Los archivos temporales, cachés, sesiones, logs y vistas compiladas son generados automáticamente por Laravel y no necesitan almacenarse en el repositorio.

## Estructura principal

```text
taskboard/
├── app/
├── bootstrap/
├── config/
├── database/
├── public/
├── resources/
├── routes/
├── storage/
├── tests/
├── .env.example
├── .gitignore
├── artisan
├── composer.json
├── composer.lock
├── package.json
├── phpunit.xml
└── vite.config.js
```

## Comandos útiles

Limpiar cachés de Laravel:

```bash
php artisan optimize:clear
```

Ejecutar migraciones:

```bash
php artisan migrate
```

Ejecutar pruebas:

```bash
php artisan test
```

Actualizar dependencias de Composer:

```bash
composer update
```

## Importante para GitHub

Antes de hacer `git add .`, verifica que **no estés agregando**:

```text
.env
/vendor
/node_modules
```

El archivo `.gitignore` incluido en este proyecto ya está configurado para ignorarlos.

## Tecnologías

- Laravel 13
- PHP 8.3+
- Composer
- SQLite
- Vite
- Node.js / npm
