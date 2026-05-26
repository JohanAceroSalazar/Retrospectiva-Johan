# Retrospectiva-Johan

## Resumen general
Este documento agrupa los hallazgos de la aplicación y muestra los problemas más importantes detectados durante la prueba. Cada capturas tiene referencia numérica y una breve descripción para facilitar el seguimiento.

## Problemas principales
1. Formulario no guarda datos correctamente.
2. Interfaz inconsistente y elementos visuales poco legibles.
3. Falta de validaciones en formularios y catálogos.
4. Control de roles y permisos mal implementado.
5. Errores en el manejo de tareas: fechas, edición y presentación.

## Recomendaciones clave
- Validar todos los formularios antes de guardar.
- Mejorar la experiencia de usuario en los inputs y títulos.
- Añadir buscador en catálogos por nombre e ID.
- Restringir cambios de rol solo a perfiles autorizados.
- Forzar fecha de vencimiento y prohibir tareas con fechas pasadas.

## Detalle de hallazgos

### 1. Formulario no guarda información
- Captura: ![Formulario no guarda](Captura%20de%20pantalla%202026-05-26%20095228.png)
- Problema: el formulario parece aceptar datos, pero no persiste la información.
- Sugerencia: revisar el envío de datos y la respuesta del backend.

### 2. Interfaz de usuario deficiente
- Captura: ![Interfaz pobre](Captura%20de%20pantalla%202026-05-26%20095325.png)
- Problemas:
  - Mala interfaz general.
  - Texto en mayúsculas sostenidas sobre inputs.
- Sugerencia: usar texto normal y un diseño más limpio.

### 3. Alineación y acceso no deseado
- Captura: ![Alineación rota](Captura%20de%20pantalla%202026-05-26%20095423.png)
- Problemas:
  - Texto no encaja con los cuadros de texto.
  - Se puede acceder a OpenAPI/Swagger desde la interfaz.
- Sugerencia: corregir el layout y ocultar herramientas de desarrollo a usuarios finales.

### 4. Catálogos sin validaciones y sin búsqueda
- Captura: ![Catálogos sin validación](Captura%20de%20pantalla%202026-05-26%20095725.png)
- Problemas:
  - Se acepta texto numérico en el campo “nombre”.
  - No existe buscador para filtrar catálogos por id o nombre.
- Sugerencia: agregar validaciones de tipo y búsqueda inteligente.

### 5. Desactivación de roles sin control
- Captura: ![Roles mal controlados](Captura%20de%20pantalla%202026-05-26%20100106.png)
- Problema: cualquier persona puede desactivar un rol de usuario.
- Sugerencia: limitar esta acción a administradores o a perfiles con permiso específico.

### 6. Cambio de rol inseguro
- Captura: ![Cambio de rol inseguro](Captura%20de%20pantalla%202026-05-26%20100238.png)
- Problema: se permite convertir fácilmente un abogado en administrador.
- Sugerencia: validar permisos y exigir autorización para cambios de rol críticos.

### 7. Tablero de tareas demasiado largo
- Captura: ![Tablero de tareas largo](Captura%20de%20pantalla%202026-05-26%20101317.png)
- Problema: el tablero ya aparece muy extenso desde el inicio.
- Sugerencia: cargar tareas dinámicamente o mostrar solo las más recientes.

### 8. Creación de tareas sin restricciones
- Captura: ![Tareas sin control](Captura%20de%20pantalla%202026-05-26%20101747.png)
- Problemas:
  - Se aceptan fechas anteriores.
  - Se permite crear sin fecha de vencimiento.
  - No hay restricciones en el nombre.
  - No se puede actualizar la tarea para corregir errores.
- Sugerencia: aplicar reglas de validación estrictas y habilitar edición.

### 9. Presentación desordenada de tareas
- Captura: ![Presentación de tareas desordenada](Captura%20de%20pantalla%202026-05-26%20102112.png)
- Problema: los cuadros y el texto no están alineados; la fecha queda corrida.
- Sugerencia: revisar el CSS de los componentes de tarea y ajustar el espaciado.

## Capturas de pantalla
1. `Captura de pantalla 2026-05-26 095228.png` - formulario no guarda.
2. `Captura de pantalla 2026-05-26 095325.png` - interfaz y mayúsculas.
3. `Captura de pantalla 2026-05-26 095423.png` - alineación y acceso OpenAPI.
4. `Captura de pantalla 2026-05-26 095725.png` - validaciones en catálogos.
5. `Captura de pantalla 2026-05-26 100106.png` - control de desactivación de roles.
6. `Captura de pantalla 2026-05-26 100238.png` - cambio de rol inseguro.
7. `Captura de pantalla 2026-05-26 101317.png` - tablero de tareas largo.
8. `Captura de pantalla 2026-05-26 101747.png` - creación de tareas sin restricciones.
9. `Captura de pantalla 2026-05-26 102112.png` - presentación de tareas desordenada.

## Próximos pasos
- Priorizar las correcciones de validación y permisos.
- Mejorar el diseño visual de inputs y tarjetas.
- Añadir un buscador para catálogos y filtros de tarea.
- Probar nuevamente con usuarios reales tras los cambios.
