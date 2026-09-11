# GestFincas

GestFincas es una aplicación web desarrollada en PHP para la gestión integral de comunidades de vecinos. Su objetivo es centralizar la administración diaria de una comunidad mediante herramientas que permiten controlar viviendas, usuarios, comunicaciones, incidencias, reuniones, votaciones, finanzas y reservas de espacios comunes desde una única plataforma.

La solución está diseñada bajo el patrón de arquitectura MVC (Modelo-Vista-Controlador), con una base de datos relacional en MySQL. Esta estructura facilita la mantenibilidad, escalabilidad y evolución del sistema, permitiendo añadir nuevas funcionalidades sin romper la lógica existente.

---

## Descripción del proyecto

GestFincas ayuda a organizar y automatizar la gestión de una comunidad de propietarios o vecinos de una forma clara, eficiente y segura. Con esta aplicación, la administración puede llevar el control de los procesos más habituales de la comunidad desde un mismo punto de acceso.

El sistema está pensado para cubrir las necesidades tanto de presidentes o administradores como de los vecinos, adaptando la experiencia según el rol del usuario.

---

## Objetivos

- Facilitar la administración de viviendas y usuarios.
- Mejorar la comunicación interna entre vecinos y administración.
- Gestionar de forma ordenada las reservas de espacios comunes.
- Centralizar la información financiera y de cuotas.
- Organizar reuniones, votaciones e incidencias.
- Proporcionar una herramienta útil, accesible y segura para la comunidad.

---

## Funcionalidades principales

### 1. Autenticación y gestión de usuarios

- Registro de usuarios asociados a una vivienda.
- Inicio de sesión con validación de credenciales.
- Diferenciación de roles entre vecino y presidente.
- Control de acceso según el perfil del usuario.

### 2. Administración de viviendas y comunidad

- Registro y gestión de viviendas.
- Relación entre usuarios, comunidad y domicilio.
- Organización de la estructura interna de la comunidad.

### 3. Comunicaciones y avisos

- Publicación de comunicados y noticias internas.
- Visualización de mensajes relevantes para la comunidad.
- Difusión de información útil para todos los vecinos.

### 4. Reuniones y votaciones

- Programación y gestión de reuniones comunitarias.
- Creación de votaciones o consultas.
- Seguimiento de decisiones colectivas.

### 5. Reservas de espacios comunes

- Gestión de recursos compartidos como patios, salas o zonas comunes.
- Control de disponibilidad.
- Registro histórico de reservas realizadas.

### 6. Incidencias

- Apertura de incidencias por parte de los usuarios.
- Seguimiento del estado de resolución.
- Organización del flujo de trabajo para atender averías y problemas.

### 7. Finanzas

- Gestión de cuotas y pagos.
- Control de gastos y facturas.
- Seguimiento del estado financiero de la comunidad.

### 8. Proveedores

- Gestión de proveedores asociados a la comunidad.
- Registro de servicios contratados.
- Consulta de información útil para la administración.

---

## Arquitectura del proyecto

La aplicación sigue una estructura basada en MVC:

- Modelo: gestiona la lógica de acceso y manipulación de datos.
- Vista: contiene la interfaz de usuario y los componentes visuales.
- Controlador: procesa las peticiones y coordina la lógica de negocio.

## Estructura principal

```text
gestfincas/
├── config/
│   ├── database.php
│   ├── router.php
│   ├── gestfincas.sql
│   ├── config.php.example
│   └── config.local.php
├── public/
│   ├── index.php
│   └── assets/
├── src/
│   ├── controllers/
│   ├── models/
│   ├── views/
│   └── ...
├── libs/
│   ├── dompdf/
│   └── PHPMailer/
├── index.php
├── README.md
├── test_pdf.php
└── ...

---

## Crear la base de datos

1. Inicia Apache y MySQL desde el panel de control de XAMPP.
2. Accede a phpMyAdmin.
3. Crea una base de datos llamada `gestfincas`.
4. Importa el archivo `config/gestfincas.sql`.

Esto generará todas las tablas necesarias para el funcionamiento de la aplicación.

---

## Configurar la base de datos

1. Crea el archivo `config.local.php` a partir de `config.php.example`
2. Ajusta los datos de conexión según el ejemplo descirto abajo con tus credenciales locales:

<?php
return [
    'host'    => 'localhost',
    'db'      => 'gestfincas',
    'user'    => 'root',
    'pass'    => '',
    'charset' => 'utf8mb4'
];
?>

---

## Ejecutar la aplicación

1. En tu navegador acceso index para rol usuario / presidente: http://localhost/proyectos/gestfincas/index.php
2. En tu navegador acceso index para rol administrador: http://localhost/proyectos/gestfincas/index.php?route=superadmin/login
2. Si la carpeta del proyecto tiene un nombre distinto, adapta la ruta según el directorio exacto en el que lo hayas ubicado.

---

## Datos de prueba

El archivo SQL incluye usuarios y registros iniciales para facilitar la validación del sistema, y así probar el flujo de login y la navegación con esos datos predefinidos.

| Rol           | Comunidad        | Vivienda | Mail                  | Password   |
|---------------|------------------|----------|---------------------- |------------|
| Presidente    | Las Flores       | Piso 1-C | josemoreno@gmail.com  | jose123    |
| Vecino 1      | Las Flores       | Piso 2-C | mariapelaez@gmail.com | maria123   |
| Vecino 2      | Los Cerezos      | Piso 5-B | teresaperez@gmail.com | teresa123  |
| Administrador | -                | —        | admin@gestfincas.com  | password   |

---

## Casos de uso habituales

1. Un vecino da de alta su vivienda y accede a su panel.
2. Un presidente gestiona reuniones, comunicaciones y finanzas, entre otras.
3. El presidente controla incidencias y la disponibilidad de recursos.
4. La comunidad consulta avisos, cuotas y resoluciones de forma centralizada.

---

## Licencia

Proyecto realizado bajo marco de prácticas FP. Orientado exlusivamente a uso académico.



