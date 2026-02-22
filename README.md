# Pendientes — Documentación

Una página local para gestionar tareas escolares, sin necesidad de internet ni cuenta.

---

## Estructura

La página está hecha en un solo archivo HTML con tres partes:

**HTML** — Define los elementos visibles: encabezado, botón de borrar todo, lista de tareas, barra de progreso y formulario para agregar.

**CSS** — Estilos visuales. Fondo negro, colores fríos (azul, índigo, verde agua), tipografías Syne y Space Mono.

**JavaScript** — Toda la lógica: agregar tareas, marcarlas como completadas, eliminarlas individualmente, borrar todo, calcular el progreso y guardar en localStorage.

---

## Cómo funciona

- Al agregar una tarea se guarda automáticamente en el `localStorage` del navegador.
- Al recargar la página, las tareas se recuperan desde ahí, por eso persisten entre sesiones.
- La barra de progreso se actualiza en tiempo real según cuántas tareas están completadas.
- Cada tarea recibe un color automático en orden de una paleta predefinida.

---

## Formulario para agregar tareas

| Campo | Obligatorio | Descripción |
|---|---|---|
| Nombre | ✅ | Título de la tarea |
| Materia | ❌ | Categoría (si se omite queda como "Otro") |
| Descripción | ❌ | Detalle adicional de la tarea |

Puedes presionar `Enter` desde cualquier campo de texto para agregar la tarea.

---

## Acciones sobre tareas

- **Completar** — Click sobre la tarea para marcarla/desmarcarla.
- **Eliminar una** — Pasar el cursor sobre la tarea y presionar el botón `✕` que aparece a la derecha.
- **Borrar todo** — Botón ⚠ en la esquina superior derecha del encabezado.

---

## Botón "Borrar todo"

Al presionar **⚠ Borrar todo** aparece un modal de confirmación antes de ejecutar cualquier acción. Desde ahí puedes cancelar o confirmar. Si confirmas, se ejecuta:

```js
localStorage.removeItem('pendientes')
```

La lista queda vacía de inmediato. También puedes cerrar el modal clickeando fuera de él.

---

## Limpiar el localStorage manualmente desde la consola

Si necesitas hacerlo sin usar el botón:

1. Abre el navegador en la página
2. Presiona `F12` para abrir las DevTools
3. Ve a la pestaña **Console**
4. Escribe el siguiente comando y presiona Enter:

```js
localStorage.removeItem('pendientes')
```

5. Recarga la página con `F5`

---

> El archivo no necesita servidor ni instalación. Se abre directo en el navegador.