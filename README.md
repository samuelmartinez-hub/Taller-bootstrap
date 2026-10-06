# Cilindro: rediseño de la página de un taller de motos con Bootstrap 5

**Estudiante:** Samuel Martínez Bayona
**Código:** 019-2703
**Asignatura:** Desarrollo de Aplicaciones Web
**Actividad:** Taller "Rediseñando una Página Web"

Página de una sola vista para un taller de motos ficticio llamado Cilindro. Tiene header con logo y navegación, hero con título, subtítulo y botón de llamada a la acción, grilla de 3 servicios, formulario para agendar una revisión y footer con enlaces y créditos.

## Cómo abrirla

No necesita instalación ni build. Basta con abrir `index.html` en el navegador con conexión a internet, porque Bootstrap, los iconos y las tipografías de Google Fonts se cargan por CDN.

```
taller-bootstrap-motos/
├── index.html
├── README.md
└── capturas/
```

## Por qué elegí Bootstrap y no Tailwind

Elegí la **Opción B: Bootstrap 5**. Estas son las razones, en el orden en que pesaron.

**1. Velocidad de arranque.** En la tabla comparativa de la clase, Bootstrap tiene la velocidad inicial "muy alta" y es lo que más se nota al trabajar. La barra de navegación que se colapsa en móvil, la grilla de tarjetas, el formulario con sus mensajes de validación y la alerta de confirmación ya existen como componentes (`navbar`, `row-cols-md-3`, `form-control`, `invalid-feedback`, `alert`). Solo tuve que armarlos y ajustar el contenido. Con Tailwind habría tenido que componer cada uno desde clases utilitarias.

**2. Menos clases en el HTML.** La clase marca la densidad de clases de Bootstrap como "media" frente a "alta" en Tailwind, y se nota: una tarjeta de servicio es un `card` con `card-body` y unas pocas utilidades de espaciado, y el código se lee casi como una descripción de lo que hace cada bloque.

**3. Componentes con comportamiento incluido.** El menú móvil, la validación del formulario y el estado de error de cada campo funcionan con el JavaScript de Bootstrap y muy poco código propio. Además usé Bootstrap Icons para los iconos de los servicios, sin dibujar nada a mano.

**4. Responsivo con pocas decisiones.** La grilla de servicios usa `row row-cols-1 row-cols-md-3`: una columna en móvil y tres desde pantallas medianas. El formulario usa `col-md-6` para pasar de campos apilados a dos columnas.

## Cómo apliqué las buenas prácticas de la clase

**No luchar contra el framework.** Para cambiar el color principal a rojo y las fuentes no sobrescribí los estilos de cada componente con selectores propios. Redefiní las variables que Bootstrap ya ofrece (`--bs-primary`, `--bs-body-font-family`, `--bs-btn-bg`) y el resto se adapta solo.

**Semántica HTML.** Usé `header`, `nav`, `main`, `section`, `article` para cada servicio, `footer`, y `label` enlazado a cada campo del formulario, en lugar de llenar la página de `div`.

**Personalizar el tema a nivel global.** Los colores (asfalto, rojo, cromo) y las tipografías se definen una sola vez en `:root` y se reutilizan en toda la página.

## Lo que me costó o no es ideal de Bootstrap

**Personalización limitada.** La tabla de clase dice que en Bootstrap la personalización visual se limita a las variables de tema, y lo comprobé. Para que la página no se viera como "una página Bootstrap más" tuve que escribir un bloque pequeño de CSS propio (colores, tipografías, el borde rojo de las tarjetas y los iconos). Con Tailwind eso se resuelve con clases sin salir del HTML.

**Se carga el framework completo.** Usé el CDN con todo Bootstrap, aunque solo ocupo una parte de sus componentes. La clase recomienda importar solo los componentes necesarios para optimizar el bundle final, y eso requiere compilar con Sass, algo que el taller no pide para un solo `index.html`. Para un proyecto real lo haría.

## Detalles de calidad

- Contraste de color revisado en textos y botones.
- Foco de teclado visible en enlaces, botones y campos.
- Validación del formulario con los estilos de Bootstrap: los campos incorrectos muestran un mensaje que explica cómo corregirlos.
- Los botones de cada servicio preseleccionan esa opción en el formulario.
- El formulario no se conecta a ningún servidor; al enviarlo solo muestra una confirmación en pantalla.
# Taller-bootstrap
