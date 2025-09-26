# Ofrenda de Día de Muertos

**Un homenaje a las mujeres que iluminaron la tecnología.**

Este proyecto es una conmemoración para honrar a mujeres extraordinarias de la historia de la computación y la ciencia. El sitio muestra una ofrenda con **calaveras mexicanas** (una por cada mujer), y al pasar el cursor o tocar en móvil, aparece una tarjeta con sus aportes y una breve reseña.

---

## 🛠️ Cómo contribuir (¡PRs bienvenidos!)

Nos encantaría sumar más perfiles de mujeres en tecnología. Si quieres agregar una, **abre un Pull Request** con los cambios.

### Pasos rápidos

1. **Fork** de este repositorio.
2. Crea una rama: `git checkout -b feat/nuevo-perfil`.
3. Edita `index.html` y agrega un objeto más en el arreglo `mujeres` (ver abajo).
4. Prueba localmente (abre `index.html` en el navegador).
5. **Commit + push** y abre tu **PR** describiendo:

   * nombre completo, fechas (si aplica)
   * 3–4 líneas de bio
   * 1–2 líneas con su contribución clave
   * 1–2 fuentes de referencia (links)

> **Tip:** El orden del arreglo se usa para el grid 3×3 de izquierda a derecha y de arriba hacia abajo.

---

## ➕ Dónde agregar un perfil

Busca esta sección en `index.html` y agrega un nuevo objeto dentro de `const mujeres = [ ... ]`:

```js
const mujeres = [
  { nombre: 'Ada Lovelace (1815–1852)', bio: 'Primera programadora. Creó el primer algoritmo destinado a ser procesado por una máquina.', contrib: 'Anticipó el software moderno.', theme: { base:'#ffe3ef', ring:'#f59e0b', accent:'#6a1b9a', nose:'heart', band:'#fef3c7' } },
  { nombre: 'Annie Easley (1933–2011)', bio: 'Científica de la NASA.', contrib: 'Desarrolló e implementó un código informático que analizaba tecnologías de energía alternativa, y facilitó el surgimiento de los cohetes de fase superior denominados Centaur.', theme: { base:'#eef2ff', ring:'#6a1b9a', accent:'#f59e0b', nose:'drop', band:'#fff3cf' } },
  { nombre: 'Anita Borg (1949–2003)', bio: 'Científica informática.', contrib: 'En 1994 creó la Celebración Grace Hopper de Mujeres en la Informática con el objetivo de apoyar la incorporación de las mujeres a la tecnología.', theme: { base:'#fff0f0', ring:'#e91e63', accent:'#1565c0', nose:'diamond', band:'#fff2cc' } },
  { nombre: 'Betty Snyder Holberton (1917-2001)', bio: 'Pionera de la computación, una de las seis programadoras originales del ENIAC.', contrib: 'Contribuyó al desarrollo del primer lenguaje de programación y a la invención de los "puntos de interrupción" (breakpoints) para la depuración de software.', theme: { base:'#ffe3ef', ring:'#f59e0b', accent:'#6a1b9a', nose:'heart', band:'#fef3c7' } },
  { nombre: 'Dorothy Vaughan (1910–2008)', bio: 'Jefa de programación en NACA/NASA.', contrib: 'Pionera en Fortran. Después de convertirse en una experta en programación, el trabajo matemático de Vaughan permitió que John Glenn fuese el primer astronauta estadounidense en hacer una órbita completa de la Tierra.', theme: { base:'#fffbe6', ring:'#f59e0b', accent:'#6a1b9a', nose:'tri-heart', band:'#ffefbf' } },
  { nombre: 'Grace Hopper (1906–1992)', bio: 'Pionera de compiladores y COBOL.', contrib: 'Construyó el primer compilador. Sus trabajos sentaron las bases para el desarrollo de la informática tal como la conocemos hoy, impulsando la revolución del software.', theme: { base:'#e5f0ff', ring:'#1565c0', accent:'#ff7a59', nose:'spade', band:'#fff4d3' } },
  { nombre: 'Hedy Lamarr (1914–2000)', bio: 'Inventora del salto de frecuencia.', contrib: 'Base para Wi‑Fi, Bluetooth y GPS.', theme: { base:'#ffeaf7', ring:'#ff00a6', accent:'#16a34a', nose:'diamond', band:'#fff1c2' } },
  { nombre: 'Katherine Johnson (1918–2020)', bio: 'Matemática, física y científica espacial estadounidense.', contrib: 'Reconocida por sus esenciales cálculos para la NASA que posibilitaron los primeros vuelos espaciales tripulados de EE. UU., incluyendo el exitoso aterrizaje lunar de la misión Apolo 11.', theme: { base:'#eef9ff', ring:'#8dd0ff', accent:'#6a1b9a', nose:'triangle', band:'#fdf5d6' } },
  { nombre: 'Margaret Hamilton (1936–)', bio: 'Lideró el software de Apolo.', contrib: 'Sistema de prioridades que salvó el alunizaje.', theme: { base:'#fff6e5', ring:'#f59e0b', accent:'#1565c0', nose:'club', band:'#ffe9b5' } }
];
```

### Ejemplo de un nuevo objeto

```js
{
  nombre: 'Nombre Apellido (YYYY–YYYY|—)',
  bio: '1–3 líneas con contexto de su trabajo e impacto.',
  contrib: 'La contribución clave en 1–2 líneas.',
  theme: {
    base:'#fff6e5',     // color base del cráneo
    ring:'#f59e0b',     // anillo alrededor de los ojos
    accent:'#1565c0',   // color de la nariz/decorados
    nose:'heart',       // forma de la nariz: heart | spade | diamond | triangle | club | leaf | drop | tri-heart
    band:'#ffe9b5'      // banda del nombre en la frente
  }
}
```

> **Nota:** El texto del nombre se auto‑acomoda para evitar desbordes (auto‑fit). Usa tildes y caracteres especiales correctamente.

---

## Estructura del proyecto

* `index.html` — Todo el sitio (HTML, CSS y JS en un solo archivo).
* **Generación SVG**: cada calavera se dibuja por código (ojos con flores, nariz temática, banda con nombre) y muestra un **tooltip** con bio + contribución al hacer hover/tap.
* **Decoración**: papel picado curvo en la parte superior, velas y cempasúchil al pie.

---

## 🧪 Pruebas ligeras (en consola)

Hay pequeñas aserciones en consola para validar que:

* `renderSkullSVG` devuelve un string.
* `nameScale` reduce nombres largos y nunca excede el ancho.
* El arreglo `mujeres` tiene la longitud esperada para el grid.

Si agregas perfiles, confirma que la consola no muestre errores.

---

## Desarrollo local

* **Opción 1:** abre `index.html` directamente en tu navegador.
* **Opción 2 (servidor local):**

  ```bash
  # con Python 3
  python -m http.server 8080
  # o con Node
  npx serve
  ```

  Luego visita `http://localhost:8080`.

---

## 🤝 Guía de contribución

* Aporta perfiles de mujeres en tecnología de cualquier época o región.
* Mantén un **tono respetuoso** y **fuentes confiables** (agrega enlaces en el PR).
* Bio corta (hasta ~300 caracteres) y contribución clara.
* Revisa ortografía y acentos; usa nombres completos.

Si tienes dudas, abre un issue antes del PR.

---

## Licencias y créditos

* **Arte/Decoración generada por código:** libre de uso dentro de este proyecto.
* Si usas assets externos (íconos, imágenes), incluye su **atribución y licencia** en el PR.

> Hecho con respeto y cariño por **[Michelle](https://algorithmich.github.io/)** para **[TechnoLatinas](https://technolatinas.org/)** 💜
---

## 💡 Ideas futuras

* Añadir más mujeres y categorías (p. ej., redes, IA, hardware, educación).
* Localización completa (ES/EN/PT) con toggles.
* Filtros y búsqueda por nombre o área.
* Modo alto contraste y mejoras de accesibilidad.
