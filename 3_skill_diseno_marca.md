# Skill: Diseño Industrial "Manos Sucias" y Marca Taller Don Ramiro

## Cuándo usar este Skill
Aplica estas directrices obligatoriamente al diseñar, estructurar o modificar cualquier componente visual del archivo `index.html` del Taller Don Ramiro.

## 1. Ergonomía "Manos Sucias" (Vista Mecánico)
- **Tema:** Modo oscuro industrial de alto contraste (`bg-slate-950`, tarjetas `bg-slate-900`, texto `text-white`) para evitar reflejos bajo luz de taller y disimular manchas en pantalla.
- **Áreas de Toque (Touch Targets):** Todos los botones operativos (selector `Mecanico1-4`, cambio de estado, micrófono, botones `+$10/+$20/+$50` y `Otro Monto`) deben tener una altura mínima de `56px` a `64px`, bordes redondeados (`rounded-xl`) y separación mínima de `12px` para evitar toques accidentales con dedos engrasados.
- **Tipografía:** Sans-serif clara y robusta (`Inter` o `Segoe UI`), montos en fuente monoespaciada grande (`text-2xl font-bold`) y placas vehiculares con estilo de matrícula metálica.

## 2. Semáforo Semántico de Estados (Colores Oficiales)
1. `📥 Recibido`: Gris (`#64748b` / `slate-500`)
2. `🔍 En Diagnóstico`: Azul Rey (`#2563eb` / `blue-600`)
3. `⏸️ Pausado: Esperando Aprobación`: Ámbar/Rojo Alerta (`#dc2626` / `red-600` con borde pulsante)
4. `🔧 En Reparación`: Amarillo Industrial (`#eab308` / `yellow-500`)
5. `✅ Listo para Entregar`: Verde Éxito (`#16a34a` / `green-600`)

## 3. Estética de Confianza (Vista Cliente y Vista Don Ramiro)
- **Tema:** Modo claro ejecutivo (`bg-slate-50`, tarjetas blancas `bg-white`, acentos en Azul Rey `#1e40af`).
- **Comprobante Digital Inmutable:** Diseño tipo recibo bancario con borde punteado o sello verde de verificación, mostrando hash/ID de transacción en tipografía monoespaciada.