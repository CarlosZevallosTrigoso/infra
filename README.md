# Matrices · antropología de las infraestructuras

Sitio estático para GitHub Pages: matrices analíticas de las lecturas del círculo y un lector anotador de los textos.

## Estructura

- `index.html` — índice: los tres textos, genealogía, matriz comparativa y conceptos que viajan.
- `star-ruhleder-1994.html`, `star-1999.html`, `harvey-jensen-morita-2016.html` — matrices analíticas (con modo hilo, mapa de sustento y enlaces al lector).
- `lector.html` — lector y anotador de Markdown. Se abre con `lector.html?f=<archivo.md>`; acepta `&p=<página>` para saltar a una página y `&q=<texto>` para ir a una cita y resaltarla. Sin parámetros, muestra la lista de lecturas.
- `marked.umd.js` — conversor Markdown→HTML local (sin CDN).
- `lecturas/` — los `.md` de los textos, con sus nombres originales.
- `.nojekyll` — vacío; impide que GitHub Pages convierta los `.md` en HTML (sin él, el lector recibe un 404).

## Agregar un texto al lector

Sube su `.md` a `lecturas/` y ábrelo con `lector.html?f=<nombre>.md`. Para que aparezca en la lista inicial, con su título, su desfase de páginas y su matriz, agrega una entrada a `LECTURAS` dentro de `lector.html`. Las marcas `{n}----` de la conversión se muestran como página `n + 1 + desfase`.

## Comentarios fijos

Si junto a un texto existe `lecturas/<nombre-del-texto>.comentarios.json`, el lector lo carga al abrirlo y muestra esos comentarios en azul, de solo lectura, intercalados por posición en el panel. Se pueden ocultar en «ajustes». El formato es el mismo que produce «exportar .json» del lector: para fijar anotaciones propias basta con exportarlas, renombrar el archivo con el sufijo `.comentarios.json` y subirlo a `lecturas/`. Las anotaciones personales con el mismo identificador que una fija se retiran del navegador para no duplicarse.

## Notas

- Las anotaciones del lector se guardan en el navegador, por texto, y se pueden exportar e importar como `.json`.
- Abrir los archivos con doble clic (`file://`) no carga los `.md`; hay que verlos publicados en Pages o con un servidor local (`python3 -m http.server`).
