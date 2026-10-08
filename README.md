# Gestor ADSO con Laravel

Este proyecto corresponde a la evidencia técnica individual para la formación técnica del **SENA (TACA Class)**. Contiene la instalación, configuración inicial y despliegue del entorno local del proyecto `gestor-adso`.

## 1. Versiones del Entorno Utilizadas
* **Sistema Operativo:** Windows 11
* **Git:** 2.55.0.windows.3
* **Laravel Framework:** 12.69.3
* **Gestor de Base de Datos:** MariaDB / MySQL (XAMPP)

---

## 2. Pasos de Instalación y Despliegue

### Paso 1: Clonar o Inicializar el Repositorio
Si se inicia desde cero en el entorno local:
```bash
git init
git add .
git commit -m "Initial commit"
```

### Paso 2: Instalación de Dependencias
Para reconstruir el directorio `vendor` y las dependencias de PHP necesarias para el Framework:
```bash
composer install
```

### Paso 3: Configuración del Entorno (.env)
Copiar el archivo de plantilla de entorno local e inicializar la clave de seguridad del proyecto:
```bash
cp .env.example .env
php artisan key:generate
```

---

## 3. Variables Requeridas del .env (Estructura de Base de Datos)
Para la conexión con el servidor local de base de datos se requiere la base de datos `gestor_adso`. Las credenciales locales se manejan bajo estricta seguridad sin exponer contraseñas en el repositorio:

```ini
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=gestor_adso
DB_USERNAME=root
DB_PASSWORD=********
```

---

## 4. Comandos de Migración
Antes de migrar, se ejecuta la limpieza preventiva de la caché de configuración. Posteriormente, se procesan las migraciones iniciales para poblar las tablas en MariaDB:

```bash
php artisan config:clear
php artisan migrate
```

---

## 5. Ejecución del Proyecto
Para levantar el servidor de desarrollo local integrado en Laravel y validar el acceso en el navegador web:

```bash
php artisan serve
```
* Servidor operativo localmente en la dirección IP: `http://127.0.0.1:8000`
