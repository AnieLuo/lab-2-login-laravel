LABORATORIO N°2 - CIERRE

INTRODUCCIÓN

Este laboratorio tuvo como objetivo comprender la estructura básica de un proyecto en Laravel bajo el patrón Modelo-Vista-Controlador (MVC), así como implementar el módulo de login y registro de usuarios.
Laravel organiza sus proyectos en torno a la arquitectura MVC:

⦁	Modelos: Representan la lógica y estructura de datos.

⦁	Vistas: Definen la interfaz que interactúa con el usuario.

⦁	Controladores: Contienen la lógica que conecta los modelos con las vistas.

⦁	Rutas: Definen cómo se redirigen las peticiones HTTP hacia los controladores.

Además, se trabajó con migraciones para generar las tablas necesarias en la base de datos.

REQUISITOS PREVIOS

Para ejecutar este laboratorio, se utilizó el siguiente ecosistema de desarrollo:

⦁	PHP 8.2.26

⦁	Composer (última versión estable)

⦁	Laravel (instalación mediante composer create-project)

⦁	Servidor local: WampServer

⦁	Base de datos: MySQL (phpMyAdmin)

⦁	Editor: Visual Studio Code

⦁	Node.js y npm (para compilación de assets front-end)

⦁	Sistema operativo: Windows 10

⦁	Dependencias y Comandos principales:

	# Creación de proyecto
    
	composer create-project laravel/laravel login-lab
    
	# Instalación de dependencias
    
	composer install
    
	# Generación de clave
    
	php artisan key:generate
    
	# Migraciones
    
	php artisan migrate
    
	php artisan migrate:fresh
    
	# Instalación de UI para autenticación
    
	composer require laravel/ui
    
	php artisan ui bootstrap --auth
    
	# Compilación de assets
    
	npm install
    
	npm run dev

FLUJO DE TRABAJO

1.	Configuración del entorno de PHP y Composer.
2.	Creación del proyecto Laravel.
3.	Configuración del archivo .env con la base de datos.
4.	Generación de la clave de aplicación (APP_KEY).
5.	Ejecución de migraciones.
6.	Instalación del paquete de autenticación.
7.	Instalación de Node.js y compilación de assets.
8.	Despliegue del servidor y verificación del login y registro.

RESULTADOS

El sistema permitió:

⦁	Registro de nuevos usuarios.

⦁	Inicio de sesión exitoso.

⦁	Verificación de datos en la base de datos.


BASE DE DATOS

⦁	Se creó una base de datos en MySQL llamada lab_2_login.

⦁	Se configuró la conexión en el archivo .env:

	DB_CONNECTION=mysql
	DB_HOST=127.0.0.1
	DB_PORT=3306
	DB_DATABASE=lab_2_login
	DB_USERNAME=root
	DB_PASSWORD=
    
⦁	Migraciones aplicadas: users, password_resets, failed_jobs, personal_access_tokens.

⦁	Se utilizó el comando php artisan migrate:fresh para resolver conflictos de duplicación de tablas.

DIFICULTADES Y SOLUCIONES

⦁	PHP no reconocido en CMD

	Solución: agregar la ruta de PHP al Path de Windows.
    
⦁	Error al configurar usuario de Composer

	Solución: configuración realizada con Git en lugar de Composer.
    
⦁	No se generaba el APP_KEY

	Solución: instalar Composer antes de generar la clave.
    
⦁	Error en migración: “Specified key was too long”

	Solución: configuración de Schema::defaultStringLength(191) en AppServiceProvider.
    
⦁	Tablas duplicadas en migración

	Solución: comando php artisan migrate:fresh.
    
⦁	npm no instalado

	Solución: instalar Node.js y volver a compilar los assets.
    
⦁	Error en middleware

	Solución: cambiar App\Http\Controllers\Controller por Illuminate\Routing\Controller.

REFERENCIAS

https://laravel.com
https://stackoverflow.com/questions/35117781/class-app-http-controllers-controller-not-found-laravel-5-2
https://stackoverflow.com/questions/1814532/mysql-error-1071-specified-key-was-too-long-max-key-length-is-767-bytes
https://getcomposer.org/doc

INFORMACIÓN DEL DESARROLLADOR

Este laboratorio ha sido desarrollado por una estudiante de la Universidad Tecnológica de Panamá:

Nombre: Anie Luo

Correo: anie.luo@utp.ac.pa

Curso: Ingeniería Web

Instructor del Laboratorio: Irina Fong


FECHAS

Fecha de ejecución del laboratorio: 14 de septiembre de 2025

Fecha de entrega: 29 de septiembre de 2025
