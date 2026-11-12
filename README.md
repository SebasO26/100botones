# Catálogo de 100 botones CSS

## Archivos
- `index.html`: catálogo con los 100 botones en 10 categorías.
- `combinaciones.html`: página aparte con las 5 combinaciones de clases.
- `estilos.css`: todo el CSS (sin variables y sin JavaScript).
- `imagenes/`: dos imágenes SVG sencillas (`paisaje.svg` y `avatar.svg`).

Para verlo, abre `index.html` en el navegador.

## btn-original: técnicas usadas
1. **Forma** (categoría 2): `border-radius` de píldora.
2. **Tipografía y sombras** (categoría 3): mayúsculas, `letter-spacing` y una `box-shadow` sólida.
3. **Degradado** (categoría 4): `linear-gradient` vertical entre #064E3B y #0F766E.
4. **Transformación** (categoría 6): al interactuar sube y crece con `translateY` y `scale`.
5. **Icono** (categoría 7): una flor ✿ junto al texto, alineada con flexbox.
6. **Pseudoelemento** (categoría 8): un círculo `::before` crece desde el centro.

## Qué clase gana cuando dos modifican lo mismo
Si dos clases tienen la misma especificidad, gana la que aparece **más abajo en `estilos.css`**, no la que está escrita primero en el HTML.

- Los colores (categoría 1) están al principio, así que las formas y los efectos los respetan.
- `btn-outline` va después de los colores: en `btn btn-outline` el fondo transparente gana al de la variante.
- Los efectos `:hover` y `:focus-visible` tienen más especificidad que una clase normal, por eso `btn-hover-background` cambia el fondo de `btn-outline` al interactuar.
- `btn-glow-pulse` solo cambia `background-color`, y el degradado `btn-gradient-ocean` usa `background-image`. Por eso en la combinación 5 se ve el degradado con el brillo pulsante.
- `btn-hover-shadow` y `btn-hover-background` no repiten el color inicial: así no tapan el color de la variante.

## Notas
- El foco de teclado se ve con `:focus-visible` (contorno #111827).
- `btn-glass` y `btn-neumorphic` van dentro de un cuadro con el fondo que pide el enunciado.
- `btn-glass` usa `#1E3A8A` como fondo alternativo si el navegador no soporta `backdrop-filter`.
