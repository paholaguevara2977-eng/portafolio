# Portafolio Emmanuel — Documentación y registro (RM)

**Sitio en vivo:** https://paholaguevara2977-eng.github.io/portafolio/
**Repositorio:** https://github.com/paholaguevara2977-eng/portafolio

> Este README es el **RM del proyecto**: aquí queda registrado qué contiene el portafolio, cómo funciona, qué se ha cambiado y cómo seguir trabajando en él.

---

## 1. Descripción

Portafolio personal de Emmanuel, desarrollado con **HTML, CSS y JavaScript puro** (sin frameworks ni proceso de build). Reúne una presentación personal, servicios, habilidades, conocimientos de computación y matemática, una galería de proyectos interactivos y datos de contacto.

El sitio se publica con **GitHub Pages** desde la rama `main`.

---

## 2. Cómo verlo

- **En línea:** https://paholaguevara2977-eng.github.io/portafolio/
- **En local:** abrir `index.html` en el navegador.
- **Con servidor local (recomendado para probar):**

```bash
python -m http.server 8000
```

Luego abrir `http://localhost:8000/`.

No requiere instalar dependencias ni ejecutar compilación.

---

## 3. Estructura del proyecto

```text
portafolio/
├── index.html          # Portada: presentación, servicios, habilidades, proyectos y contacto
├── proyectos.css       # Estilos compartidos por las páginas de proyectos
├── favicon.ico         # Icono del sitio
├── horario.html        # Horario escolar (solo lectura)
├── napoleon.html
├── matematicas.html
├── especial.html
├── calculadora.html
├── reloj.html
├── memoria.html
├── tareas.html
├── clima.html
├── estadisticas.html
├── galeria.html
├── blog.html
├── encuesta.html
├── emojis.html
├── conversor.html
├── contrasenas.html
├── numero.html
├── pomodoro.html
├── cohete.html
├── flash.html
├── calendario.html
├── gato.html
├── musica.html
├── chat.html
├── buscador.html
└── lectura.html
```

Cada página incluye `favicon.ico`, enlace de vuelta al portafolio y el pie de página del proyecto.

---

## 4. Páginas y categorías

Las tarjetas de la sección **Proyectos** se filtran con el objeto `PROJECT_CATEGORIES` de `index.html`.

| Página | Descripción | Categoría |
|---|---|---|
| `napoleon.html` | Página histórica sobre Napoleón Bonaparte | Especial |
| `matematicas.html` | Quiz de matemática básica | Educación |
| `especial.html` | Exposición de computación y quiz de Excel | Educación |
| `calculadora.html` | Calculadora con operaciones básicas e historial | Herramientas |
| `reloj.html` | Reloj digital con formato de 12 y 24 horas | Herramientas |
| `memoria.html` | Juego de memoria con cartas | Juegos |
| `tareas.html` | Lista de tareas pendientes | Herramientas |
| `clima.html` | Consulta del clima por ciudad | Apps |
| `estadisticas.html` | Panel de gráficas con Chart.js | Herramientas |
| `galeria.html` | Galería de imágenes con modal | Especial |
| `blog.html` | Plantilla de blog personal | Apps |
| `encuesta.html` | Encuesta con resultados en tiempo real | Herramientas |
| `emojis.html` | Traductor de texto a emojis | Juegos |
| `conversor.html` | Conversor de unidades | Herramientas |
| `contrasenas.html` | Generador de contraseñas seguras | Herramientas |
| `numero.html` | Juego de adivinar el número | Juegos |
| `pomodoro.html` | Temporizador Pomodoro | Herramientas |
| `cohete.html` | Simulación animada de despegue | Juegos |
| `flash.html` | Tarjetas de estudio | Educación |
| `calendario.html` | Calendario interactivo con eventos | Herramientas |
| `horario.html` | Horario escolar semanal de solo lectura | Educación |
| `gato.html` | Tres en raya contra la máquina o un amigo | Juegos |
| `musica.html` | Reproductor de música | Apps |
| `chat.html` | Mini chat en línea | Apps |
| `buscador.html` | Búsqueda instantánea con filtros | Herramientas |
| `lectura.html` | Texto a voz con velocidad ajustable | Herramientas |

---

## 5. Funcionamiento de `index.html`

- **Secciones:** Inicio, Servicios, Habilidades, Computación, Matemática, Proyectos y Contacto.
- **Hero:** botones **Contáctame** y **Ver mi horario**; el segundo lleva directamente a `horario.html`.
- **Tema claro/oscuro:** el botón de la barra superior alterna el tema y guarda la preferencia en `localStorage` con la clave `theme`.
- **Habilidades:** las barras se animan al entrar en pantalla con `IntersectionObserver`.
- **Buscador de proyectos:** filtra por título y descripción en tiempo real.
- **Filtros por categoría:** Todos, Juegos, Herramientas, Educación, Apps y Especial.
- **Etiquetas:** cada tarjeta muestra su categoría mediante la clase `.category-badge`.
- **Sin resultados:** se muestra el mensaje `#noResults` cuando ningún proyecto coincide.
- **Estilos:** la portada usa CSS dentro de `index.html`; las páginas de proyectos comparten `proyectos.css`.

### Añadir un proyecto nuevo (flujo correcto)

1. Crear la página HTML con el mismo patrón visual del resto (favicon, enlace de vuelta, `proyectos.css` y pie).
2. Añadir la tarjeta dentro de `#projectsGrid` en `index.html`.
3. Registrar el archivo en `PROJECT_CATEGORIES` con su categoría:
   ```js
   'nuevo-proyecto.html': 'herramientas',
   ```
4. Probar la búsqueda y el filtro correspondiente.
5. Confirmar que aparece la etiqueta de categoría correcta.

---

## 6. `horario.html` — Horario escolar

Página añadida el **26 de octubre de 2026**.

### Funciones

- Tabla con los días que tienen clase (**lunes y viernes**) y un solo período de **3:00 a 4:00 PM**. Se quitaron los días y períodos sin clase.
- Materias fijas: **Computación** los lunes y **Matemática** los viernes, de 3:00 a 4:00 PM.
- Horario de **solo lectura**: no se puede editar desde la página.
- Botón **Entrar a las clases** con el enlace de Google Meet: https://meet.google.com/kab-jgny-ewu (abre en una pestaña nueva).
- Resalta el **día actual** y el **período de clase en curso**.
- Botones: **Ir a hoy** e **Imprimir**.
- Diseño responsive con desplazamiento horizontal en pantallas pequeñas.
- Estilos de impresión para obtener una hoja limpia en blanco y negro.

### Horario por defecto

| Período | Hora | Materia por defecto |
|---|---|---|
| 1 | 15:00 – 16:00 | Computación (lunes) / Matemática (viernes) |

### Cómo cambiar el horario

1. Editar el arreglo `DAYS` para cambiar los días visibles.
2. Editar el arreglo `ROWS` si cambian los períodos u horas.
3. Editar el objeto `DEFAULTS` para asignar las materias. Las claves siguen el formato `cell-fila-columna`, por ejemplo:
   ```js
   'cell-0-0': 'Computación'  // fila 0, lunes
   ```
   Las columnas son: 0 = lunes, 1 = viernes (solo los días incluidos en `DAYS`).
4. Guardar los cambios y volver a publicar. No hay edición ni guardado desde la página.

### Enlace de clases

- **Google Meet:** https://meet.google.com/kab-jgny-ewu
- Se muestra como botón **Entrar a las clases** en `horario.html`.

### Limitaciones conocidas

- Para cambiar el horario hay que editar el HTML y volver a publicar el sitio.
- El resaltado del día y de la hora actual depende de la fecha y hora del dispositivo.

---

## 7. Registro de cambios

| Fecha | Commit | Cambio |
|---|---|---|
| 2026-10-26 | `—` | Se quitó la edición: el horario ahora es de **solo lectura** y se eliminaron el guardado automático y los botones **Borrar materias** y **Restablecer**. |
| 2026-10-26 | `—` | Horario reducido a un solo bloque de **3:00 a 4:00 PM**: lunes Computación y viernes Matemática. Se quitaron los días y períodos vacíos. |
| 2026-10-26 | `—` | Ajuste: **lunes Computación** y **viernes Matemática**, una hora a las 3:00 PM. |
| 2026-10-26 | `—` | Se añadió el botón **Entrar a las clases** con el enlace de Google Meet en `horario.html`. |
| 2026-10-26 | `—` | Corrección: Matemática y Computación van los **lunes y viernes**, no los miércoles. |
| 2026-10-26 | `—` | Se añadieron **Matemática** y **Computación** a las 3:00 PM de los lunes y miércoles, con el bloque de tarde y el objeto `DEFAULTS`. |
| 2026-10-26 | `—` | Se añadió el botón **Ver mi horario** en el hero de la portada, con estilos para tema claro y oscuro. |
| 2026-10-26 | `76cc8e4` | Se agregó `horario.html` (horario escolar editable), su tarjeta en Proyectos y su categoría `educacion`. Verificado en local y en el sitio publicado. |
| 2026-10-26 | `75184be` | Se agregó `favicon.ico` a todas las páginas. |
| — | `f1b9c8b` | Primer commit del portafolio web. |

### Verificación realizada para `horario.html`

- Página publicada responde **HTTP 200**: `/portafolio/horario.html`.
- La portada publicada incluye la tarjeta **Horario Escolar**.
- La tabla genera 1 fila con 2 celdas de materias.
- Solo se muestran las columnas **Lunes** y **Viernes**; no quedan cuadros vacíos.
- Computación aparece el lunes y Matemática el viernes, de 3:00 a 4:00 PM.
- El horario es de **solo lectura**: no hay celdas editables, guardado automático ni botones de borrar/restablecer.
- El día actual se resalta correctamente (probado en lunes).
- El filtro **Educación** muestra 4 proyectos, incluido Horario Escolar.
- El botón **Ver mi horario** del hero apunta a `horario.html`, está centrado y se adapta a los temas claro y oscuro.
- El botón **Entrar a las clases** abre el enlace de Google Meet en una pestaña nueva.
- Sin errores en la consola del navegador.

---

## 8. Cómo continuar el proyecto (para futuras sesiones)

1. Revisar el estado del repositorio:
   ```bash
   git status
   git log --oneline -5
   ```
2. Mantener el estilo del proyecto:
   - HTML, CSS y JavaScript puro.
   - Interfaz en español.
   - Enlaces relativos entre páginas.
   - Codificación UTF-8.
   - Incluir favicon y enlace de vuelta al portafolio.
3. Reutilizar `proyectos.css` para las páginas de proyectos.
4. Probar en local con `python -m http.server` antes de publicar.
5. Hacer commit siguiendo el estilo existente (mensajes claros en español).
6. Publicar en `main`; GitHub Pages actualiza el sitio automáticamente.
7. Verificar el enlace publicado y actualizar este registro de cambios.

---

## 9. Pendientes / ideas

- [ ] Cargar el horario escolar real de Emmanuel (materias y horas definitivas).
- [ ] Añadir un enlace directo al horario en la navegación principal.
- [ ] Valorar sincronización del horario entre dispositivos (requiere backend o almacenamiento externo).
- [ ] Revisar accesibilidad de la tabla del horario (encabezados y contraste).
- [ ] Unificar estilos repetidos de las páginas de proyectos.

---

## 10. Contacto mostrado en el sitio

- Correo: `emmanuel@email.com`
- Ubicación: República Dominicana
- Usuario: `@emmanuel_dev`

---

© 2026 Emmanuel. Todos los derechos reservados.
