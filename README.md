# Sistema de Gestión y Venta de Entradas para Conciertos

## Descripción General

Este proyecto es una aplicación web desarrollada en Laravel que permite gestionar la venta de entradas para conciertos. El sistema facilita la administración de usuarios, compradores, recaudos y reservas de asientos, además de generar y enviar tickets electrónicos en formato PDF.

Su objetivo principal es automatizar el proceso de venta de entradas, mejorar el control de los eventos y mantener un registro organizado de las operaciones realizadas.

---

## Características Principales

- Administración de usuarios.
- Gestión de roles y permisos.
- Venta individual de entradas.
- Venta masiva de entradas.
- Control de disponibilidad de asientos.
- Registro de compradores.
- Generación automática de tickets en PDF.
- Envío de tickets por correo electrónico.
- Consulta de reservas y ventas.
- Gestión de recaudos.

---

## Tecnologías Utilizadas

### Backend

- PHP
- Laravel

### Base de Datos

- MySQL

### Frontend

- HTML
- CSS
- JavaScript
- Blade Templates

### Librerías

- DomPDF
- Laravel Mail

---

## Estructura General del Proyecto

```text
app/
├── Http/
│   └── Controllers/
│       ├── UserController.php
│       ├── SeatController.php
│       ├── SeatSoldController.php
│       └── CollectionController.php

├── Models/
│   ├── Seat.php
│   ├── Buyer.php
│   ├── SeatSold.php
│   ├── UsersGmos.php
│   ├── RolesGmos.php
│   └── Collection.php

routes/
└── web.php

resources/
└── views/
```

---

## Funcionamiento General

El sistema sigue la arquitectura MVC (Modelo - Vista - Controlador).

```text
Usuario
   ↓
Ruta
   ↓
Controlador
   ↓
Modelo
   ↓
Base de Datos
   ↓
Vista o Respuesta
```

---

## Proceso de Venta

Cuando un cliente realiza una compra, el sistema ejecuta las siguientes acciones:

1. Registra la información del comprador.
2. Verifica la disponibilidad del asiento.
3. Registra la venta en la base de datos.
4. Actualiza el estado del asiento a vendido.
5. Genera un ticket en formato PDF.
6. Envía el ticket al correo electrónico del comprador.

```text
Cliente selecciona asiento
           ↓
Registro de comprador
           ↓
Registro de venta
           ↓
Actualización del asiento
           ↓
Generación de PDF
           ↓
Envío por correo
```

---

## Gestión de Usuarios

El sistema permite:

- Iniciar sesión.
- Cerrar sesión.
- Crear usuarios.
- Editar usuarios.
- Eliminar usuarios.
- Asignar roles.

Dependiendo del rol asignado, el usuario tendrá acceso a determinadas funcionalidades administrativas.

---

## Gestión de Asientos

Cada asiento almacena información como:

- Número de asiento.
- Ubicación.
- Precio.
- Estado de disponibilidad.

| Estado | Descripción |
|---------|-------------|
| 0 | Disponible |
| 1 | Vendido |

---

## Gestión de Compradores

La información registrada para cada comprador incluye:

- Nombre completo.
- Correo electrónico.
- Número telefónico.
- Dirección.

Estos datos son utilizados para generar y enviar los tickets correspondientes.

---

## Gestión de Recaudos

El módulo de recaudos permite registrar:

- Valor recaudado.
- Método de pago.
- Usuario responsable.
- Fecha de registro.

Esta información facilita el seguimiento de los ingresos generados por las ventas.

---

## Generación de Tickets

Después de completar una venta, el sistema genera automáticamente un ticket digital que contiene:

- Datos del comprador.
- Información del asiento.
- Valor pagado.
- Fecha de compra.

El ticket puede descargarse o enviarse directamente al correo electrónico del cliente.

---

## Seguridad

El sistema utiliza:

- Autenticación mediante sesiones.
- Middleware para protección de rutas.
- Control de acceso basado en roles.

Esto garantiza que únicamente los usuarios autorizados puedan acceder a los módulos administrativos.

---

## Instalación

### Clonar el repositorio

```bash
git clone URL_DEL_REPOSITORIO
```

### Ingresar al directorio del proyecto

```bash
cd concierto-master
```

### Instalar dependencias

```bash
composer install
```

### Configurar variables de entorno

```bash
cp .env.example .env
```

### Generar la clave de Laravel

```bash
php artisan key:generate
```

### Ejecutar migraciones

```bash
php artisan migrate
```

### Iniciar el servidor local

```bash
php artisan serve
```

---

## Posibles Mejoras

- Recuperación de contraseña.
- Integración con pasarelas de pago.
- Reportes estadísticos.
- Auditoría de usuarios.
- Optimización de consultas a la base de datos.
- Implementación de mejores prácticas de seguridad para contraseñas.

---

## Autor

Proyecto desarrollado para la gestión y administración de eventos, permitiendo controlar ventas, compradores, recaudos y la generación automática de tickets electrónicos.
