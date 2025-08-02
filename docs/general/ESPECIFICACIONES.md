# Especificaciones Técnicas - Travel App

## 1. Descripción General
Aplicación para conectar conductores y pasajeros que comparten rutas de viaje. Objetivo principal: optimizar el uso de vehículos particulares y facilitar acuerdos de viaje compartido.

## 2. Funcionalidades Principales
- **Registro/Autenticación**:
  - Login con email/contraseña
  - Autenticación con Google/Facebook
  - Verificación de teléfono móvil

- **Creación de Viajes (Conductores)**:
  - Campos obligatorios:
    - Fecha y hora de salida
    - Origen (GPS + dirección textual)
    - Destino (GPS + dirección textual)
    - Cantidad de asientos disponibles
    - Capacidad de equipaje (Sí/No/Tamaño máximo)
    - Precio por asiento (opcional)
  - Campos opcionales:
    - Paradas intermedias
    - Reglas del viaje (ej: no fumar)
    - Descripción adicional

- **Búsqueda de Viajes (Pasajeros)**:
  - Filtros esenciales:
    - Rango de fechas
    - Hora aproximada
    - Origen/Destino (radio de 10km)
    - Cantidad de asientos requeridos
    - Necesidad de equipaje
  - Funcionalidades adicionales:
    - Guardar búsquedas frecuentes
    - Notificaciones para nuevos viajes

- **Sistema de Contacto**:
  - Integración con WhatsApp API
  - Chat interno temporal (hasta confirmación del viaje)
  - Sistema de valoraciones post-viaje

## 3. Modelo de Datos Principal
```json
{
  "Usuario": {
    "id", "nombre", "telefono", "email", "foto", "rating"
  },
  "Viaje": {
    "conductor_id", "origen", "destino", "fecha_hora",
    "asientos_disponibles", "equipaje_permitido", "estado"
  },
  "Reserva": {
    "viaje_id", "pasajero_id", "asientos_solicitados",
    "estado", "comentarios"
  }
}
```

## 4. Requisitos Técnicos
- Autenticación: Firebase Auth/Auth0
- Base de datos: PostgreSQL/MySQL
- Geolocalización: Google Maps API
- Notificaciones: Firebase Cloud Messaging

¿Qué otros aspectos deberíamos incluir o modificar en esta estructura base?"