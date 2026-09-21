# inside-terminal-web

Versión autónoma de **The Inside Market Terminal** — sin login, funciona
siempre (con la Mac apagada o prendida), porque se sirve como página
estática desde GitHub Pages en vez de depender de un servidor Flask corriendo
en una Mac.

**No reemplaza** la versión privada con login (`terminal.insidetrades.app`,
que sigue corriendo en la Mac vía Cloudflare Tunnel) — es una versión
adicional, de solo lectura, sin control de acceso.

## Cómo funciona

Esta página no tiene backend. Cada imagen se pide directo del repo público
[`inside-terminal-images`](https://github.com/jttyr/inside-terminal-images)
vía `raw.githubusercontent.com`. Ese repo lo llenan automáticamente los
workflows de `market-drivers` y `gex-terminal` en cada corrida, y se vacía
solo cada noche.

## Espacios listos para conectar después

Estos ya están en la interfaz (pestañas, banner) pero sin datos, porque
ningún workflow los publica todavía a `inside-terminal-images`:

- **Fundamental/noticias**: el banner de arriba busca
  `images/fundamental_banner.png` y `images/fundamental_full.png` en el repo
  de imágenes. Súbelos ahí (a mano, o con tu propio proceso) y aparecen
  solos — no hace falta tocar este repo.
- **Petróleo, DXY, US02Y, US10Y, US30Y**: buscan `images/OIL.png`,
  `images/DXY.png`, `images/US02Y.png`, `images/US10Y.png`,
  `images/US30Y.png` respectivamente. En cuanto algún workflow los publique
  con esos nombres exactos en `inside-terminal-images/images/`, se activan
  solos, sin tocar el código de esta página.

## Notas

La sección de Notas (`notes.html`) es igual a la de la versión privada:
vive enteramente en el navegador (`localStorage`), nunca toca ningún
servidor.
