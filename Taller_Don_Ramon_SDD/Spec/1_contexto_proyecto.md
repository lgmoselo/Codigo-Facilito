# Contexto del Proyecto: Sistema Operativo "Taller Don Ramiro"

## 1. Visión General
Aplicación web móvil (Single-Page Application) diseñada para eliminar las interrupciones por llamadas telefónicas de clientes y agilizar la aprobación de presupuestos e imprevistos mecánicos con respaldo digital inmutable.

## 2. Actores y Roles del Sistema
- **Mecánicos (`Mecanico1` a `Mecanico4`):** Usuarios operativos que trabajan únicamente desde el celular y con las manos engrasadas ("Manos Sucias"). Cada código de mecánico tiene asignado un Nombre y Apellido configurable.
- **Clientes (Portal Público sin Login):** Consultan el avance de su vehículo desde su móvil y aprueban o rechazan presupuestos iniciales e imprevistos con firma digital.
- **Don Ramiro (Administrador y Auditor):** Registra vehículos (incluyendo correo y teléfono del cliente), asigna mecánicos (`Mecanico1-4`) y audita el historial inmutable de aprobaciones.

## 3. Stack Tecnológico y Arquitectura
- **Entregable:** Aplicación autocontenida en un único archivo `index.html`.
- **Estilos:** HTML5 + Tailwind CSS (vía CDN) + Lucide Icons / FontAwesome.
- **Lógica y Persistencia:** JavaScript Vanilla (ES6+) con almacenamiento reactivo en `localStorage` para sincronizar las 3 vistas en tiempo real mediante un simulador de roles superior.
- **APIs Nativas:** `Web Speech API` (`webkitSpeechRecognition`) para dictado por voz, captura de cámara (`capture="environment"`), enlaces `wa.me` (WhatsApp) y `mailto:` (Correo Electrónico).

## 4. Fuera de Alcance (Out of Scope)
- **PROHIBIDO** incluir módulos de control de inventario de repuestos, compras o contabilidad fiscal (Don Ramiro ya administra el inventario en Excel).
- **PROHIBIDO** exigir creación de cuentas o contraseñas a los clientes.