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
├── horario.html        # Horario escolar editable
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
| `horario.html` | Horario escolar semanal editable | Educación |
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

- Tabla semanal de **lunes a viernes** con 7 períodos y un recreo.
- Materias y horas **editables**: se hace clic en una celda y se escribe.
- **Guardado automático** en `localStorage` con la clave:
  ```text
  emmanuel-horario-v1
  ```
- Resalta el **día actual** y el **período de clase en curso**.
- Botones: **Ir a hoy**, **Borrar materias**, **Restablecer** e **Imprimir**.
- Diseño responsive con desplazamiento horizontal en pantallas pequeñas.
- Estilos de impresión para obtener una hoja limpia en blanco y negro.

### Horario por defecto

| Período | Hora |
|---|---|
| 1 | 08:00 – 08:45 |
| 2 | 08:45 – 09:30 |
| 3 | 09:30 – 10:15 |
| Recreo | 10:15 – 10:45 |
| 4 | 10:45 – 11:30 |
| 5 | 11:30 – 12:15 |
| 6 | 12:15 – 13:00 |

### Cómo dejar materias fijas por defecto

Actualmente las celdas empiezan vacías y el usuario las completa. Para dejar un horario prellenado:

1. Editar el arreglo `ROWS` en `horario.html` si cambian los períodos.
2. Asignar el texto inicial a las celdas generadas, o cargar un objeto por defecto antes de `restore()`.

### Limitaciones conocidas

- El horario se guarda **solo en el navegador y dispositivo** donde se edita; no se sincroniza entre equipos.
- Si se borran los datos del navegador, se pierde el horario personalizado.
- Para compartir el horario real con todos los visitantes hay que dejarlo escrito directamente en el HTML (o usar un backend).

---

## 7. Registro de cambios

| Fecha | Commit | Cambio |
|---|---|---|
| 2026-10-26 | `—` | Se añadió el botón **Ver mi horario** en el hero de la portada, con estilos para tema claro y oscuro. |
| 2026-10-26 | `76cc8e4` | Se agregó `horario.html` (horario escolar editable), su tarjeta en Proyectos y su categoría `educacion`. Verificado en local y en el sitio publicado. |
| 2026-10-26 | `75184be` | Se agregó `favicon.ico` a todas las páginas. |
| — | `f1b9c8b` | Primer commit del portafolio web. |

### Verificación realizada para `horario.html`

- Página publicada responde **HTTP 200**: `/portafolio/horario.html`.
- La portada publicada incluye la tarjeta **Horario Escolar**.
- La tabla genera 7 filas y 30 celdas editables.
- El día actual se resalta correctamente (probado en lunes).
- Los datos persisten después de recargar (probado con “Matemática” y “Lengua Española”).
- El filtro **Educación** muestra 4 proyectos, incluido Horario Escolar.
- El botón **Ver mi horario** del hero apunta a `horario.html`, está centrado y se adapta a los temas claro y oscuro.
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
- [ ] Revisar accesibilidad de las celdas editables (roles y etiquetas ARIA).
- [ ] Unificar estilos repetidos de las páginas de proyectos.

---

## 10. Contacto mostrado en el sitio

- Correo: `emmanuel@email.com`
- Ubicación: República Dominicana
- Usuario: `@emmanuel_dev`

---

© 2026 Emmanuel. Todos los derechos reservados.
