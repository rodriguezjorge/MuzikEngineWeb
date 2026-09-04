# Muzik Engine Band — website (prototype)

Sitio estático de una sola página para **Muzik Engine Band (MEB)**, construido con el mismo
enfoque que [MedanosWeb](../MedanosWeb): HTML/CSS/JS puro, sin frameworks ni build step,
para poder publicarlo directo en GitHub Pages.

## Origen del contenido

Este es un **prototipo**. El contenido real (nombre, tagline, teléfono y email) se tomó de la
página pública de Facebook de la banda: https://www.facebook.com/bringingmusictothetop

Facebook bloquea el contenido detallado (fotos, integrantes, calendario de shows) detrás de un
login, así que esas secciones se llenaron con **fotos y video de stock (con licencia libre)**
para que la muestra se vea completa — todo listo para reemplazar por contenido real de la banda:

- **Fotos** (`images/`, `images/gallery/`, `images/services/`) — stock de
  [Unsplash](https://unsplash.com) (licencia Unsplash: uso libre comercial y personal).
- **Video** (`images/video/`) — clips de [Pexels](https://www.pexels.com) (licencia Pexels: uso
  libre, sin atribución requerida). El video de fondo del hero y la sección "Video" están
  claramente marcados en el sitio como muestra ("Sample footage for layout").
- **Repertoire** — lista de ejemplo basada en las dos canciones mencionadas en un post público
  (Venus, Bananarama); reemplázala con el setlist real.
- **Upcoming Shows** — placeholder; agrega fechas reales cuando las tengas.
- **Reviews** — el "100% recommend" sí es un dato público real de la página (7 reviews).

Para reemplazar cualquier foto o video, simplemente sobreescribe el archivo correspondiente en
`images/` (mismo nombre) o edita la ruta en `index.html`.

## Estructura

```
index.html            Página principal
styles.css             Estilos (tema negro/dorado)
script.js               Galería + menú móvil
gallery-images.json      Lista de imágenes de la galería (generada)
generate-gallery.js       Script para regenerar gallery-images.json
images/gallery/           Fotos de la galería (agrega las tuyas aquí)
```

## Cómo agregar fotos a la galería

1. Copia las imágenes (`.jpg`, `.png`, `.webp`, etc.) a `images/gallery/`.
2. Corre:
   ```bash
   node generate-gallery.js
   ```
3. Commit y push — la web las mostrará automáticamente.

## Cómo editar contenido

Todo el texto está directo en `index.html` (sin CMS ni base de datos). Busca la sección por su
`id` (`#nosotros`, `#servicios`, `#musica`, `#tour`, `#contacto`, etc.) y edita el texto.

## Deploy

Ver [DEPLOY.md](DEPLOY.md) para publicarlo en GitHub Pages, igual que MedanosWeb.
