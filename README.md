# Muzik Engine Band — website (prototype)

Sitio estático de una sola página para **Muzik Engine Band (MEB)**, construido con el mismo
enfoque que [MedanosWeb](../MedanosWeb): HTML/CSS/JS puro, sin frameworks ni build step,
para poder publicarlo directo en GitHub Pages.

## Origen del contenido

Este es un **prototipo**, pero la mayoría del contenido es **real**, tomado de la página pública
de Facebook de la banda: https://www.facebook.com/bringingmusictothetop

- **Nombre, tagline, teléfono, email, rating** — texto público de la página (Intro / About).
- **Foto de fondo del hero** (`images/hero-band.jpg`) — recortada del flyer oficial "MUZIK ENGINE
  BAND CALENDAR 2026" publicado por la banda.
- **Upcoming Shows** — el calendario completo (17 fechas, sep–dic 2026) tal cual lo publicó la
  banda, más el flyer original como poster (`images/calendar/2026-calendar.jpg`).
- **Gallery** (`images/gallery/`) — 6 flyers/artes promocionales reales tomados de las fotos
  públicas de la página de Facebook.
- **Video** — dos reels reales de la banda tocando en vivo, incrustados con el plugin oficial de
  Facebook (`facebook.com/plugins/video.php`) — no se descargó ni se re-alojó el video, solo se
  usa el reproductor embebido de Facebook (igual que un embed de YouTube).
- **Repertoire** — lista de ejemplo basada en las dos canciones mencionadas en un post público
  (Venus, Bananarama); reemplázala con el setlist real si lo tienes.
- **Reviews** — el "100% recommend" es un dato público real de la página (7 reviews).

Facebook bloquea contenido más detallado (integrantes con nombre) detrás de un login, así que
esas partes usan **fotos de stock con licencia libre** solo para que la muestra se vea completa:

- **Fotos** (`images/about.jpg`, `images/services/`, `images/music-bg.jpg`) — stock de
  [Unsplash](https://unsplash.com) (licencia Unsplash: uso libre comercial y personal).

Para agregar más reels, copia un `<iframe>` de video en `#video` con
`href=` apuntando a la URL del reel (codificada) — mismo patrón que los dos existentes.

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
