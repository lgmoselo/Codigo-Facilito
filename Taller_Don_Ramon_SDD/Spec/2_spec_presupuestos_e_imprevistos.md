# Especificación: Flujo de Diagnóstico, Imprevistos y Aprobación Digital Bilateral

## 1. Definición del Problema
Cuando un vehículo ingresa a revisión o surge una reparación adicional imprevista, el trabajo mecánico se detiene durante horas o días esperando la autorización telefónica del cliente. Además, al no existir respaldo escrito, ocurren reclamos posteriores donde el cliente desconoce haber autorizado el monto.

## 2. Diseño de la Solución

### A. Registro de Datos de Contacto (Vista Don Ramiro)
- El formulario de ingreso de vehículo exige: Nombre del Cliente, **Teléfono (WhatsApp)**, **Correo Electrónico**, Marca/Modelo, Placa y Mecánico asignado (`Mecanico1` a `Mecanico4`).

### B. Punto de Verificación 1: Diagnóstico y Presupuesto Inicial (Vista Mecánico)
1. Con el vehículo en estado `🔍 En Diagnóstico`, el mecánico ingresa el detalle de la falla mediante teclado o **botón de micrófono (Web Speech API)** y define el monto del presupuesto inicial.
2. Al pulsar `Enviar a Aprobación del Cliente`:
   - El estado cambia automáticamente a `⏸️ Pausado: Esperando Aprobación`.
   - Se habilitan dos botones de envío directo al cliente: **Enviar por WhatsApp (`wa.me`)** y **Enviar por Correo (`mailto:`)** con el resumen y enlace al portal.

### C. Punto de Verificación 2: Reporte de Imprevistos (Vista Mecánico)
1. Mediante el botón gigante `+ REPORTAR IMPREVISTO`, el mecánico:
   - Adjunta fotografía de la pieza dañada con previsualización instantánea.
   - Describe la falla por voz o texto.
   - Define el costo adicional usando botones rápidos (`+$10`, `+$20`, `+$50`) o el botón **`[ 🔢 Otro Monto ]`**, que despliega un campo numérico grande para escribir cualquier cifra exacta.
2. Al pulsar `Enviar a Aprobación del Cliente`, el auto pasa a `⏸️ Pausado: Esperando Aprobación` y se generan los enlaces de notificación por **WhatsApp y Correo Electrónico**.

### D. Aprobación con Firma y Notificación de Retorno (Vista Cliente)
1. El cliente visualiza el estado de su auto y la tarjeta destacada del Presupuesto Inicial o Imprevisto (foto, descripción y monto).
2. Marca la casilla *"Acepto el presupuesto descrito"* e introduce su firma digital (Nombre completo o últimos 4 dígitos de documento/teléfono).
3. Al pulsar `✅ APROBAR` o `❌ RECHAZAR`:
   - Si aprueba, el vehículo pasa automáticamente de `⏸️ Pausado` a `🔧 En Reparación`.
   - Se bloquea la tarjeta generando un **Comprobante Digital Inmutable** (ID único, fecha y hora exacta).
   - Se emite la **notificación del cliente hacia el taller**: alerta visual inmediata en los paneles del Mecánico y Don Ramiro + botones para que el cliente envíe su confirmación de vuelta por WhatsApp y Correo.

## 3. Criterios de Aceptación Verificables
1. **CA-01 (Contacto Dual):** Dado el formulario de nuevo vehículo, cuando Don Ramiro registra una unidad, entonces el sistema valida que existan tanto el teléfono como el correo electrónico del cliente.
2. **CA-02 (Verificación de Diagnóstico):** Dado un auto en `🔍 En Diagnóstico`, cuando el mecánico registra diagnóstico + presupuesto inicial y lo envía, entonces el auto pasa a `⏸️ Pausado` y ofrece envío por WhatsApp y Correo.
3. **CA-03 (Imprevisto con Monto Flexible):** Dado el modal de imprevistos, cuando el mecánico calcula el costo, entonces puede sumar con botones rápidos (`+$10`, `+$20`, `+$50`) o digitar un valor exacto mediante el botón `[ 🔢 Otro Monto ]`.
4. **CA-04 (Transición y Retorno al Taller):** Dado un presupuesto pendiente en el portal del cliente, cuando este firma y aprueba, entonces el auto cambia automáticamente a `🔧 En Reparación` y el sistema notifica la decisión al taller (alerta en pantalla + retorno por WhatsApp/Correo).
5. **CA-05 (Registro Inmutable):** Dada cualquier aprobación o rechazo del cliente, cuando se procesa la acción, entonces queda guardada en la tabla de auditoría de Don Ramiro con fecha, hora exacta, firma, tipo (`Diagnóstico Inicial` o `Imprevisto`) y monto bloqueado contra edición.