# Sol-4 Investment & Solicitors — Website

Website institucional de [Sol-4 Investment & Solicitors](https://sol-4gestion.com), despacho de abogados especializado en derecho inmobiliario en la Costa Blanca con 25 años de trayectoria. Sitio estático en HTML/CSS puro, sin frameworks ni dependencias de build.

---

## Estructura del proyecto

```
sol4-web/
├── index.html                        # Redirect → pages/home/
├── pages/
│   ├── home/
│   │   ├── index.html                # Página principal (con hero video)
│   │   └── styles.css                # Estilos completos de la home
│   └── home-without-video/
│       ├── index.html                # Variante sin video (fallback/test)
│       └── styles.css
├── assets/
│   ├── video/
│   │   ├── hero-opt.webm             # Hero video optimizado — WebM/VP9 (768 KB)
│   │   ├── hero-opt.mp4              # Hero video optimizado — H.264 (2.3 MB)
│   │   └── hero.mp4                  # Original sin comprimir (38 MB) — no usar en prod
│   ├── images/
│   │   ├── hero-poster.jpg           # Primer frame del hero (placeholder durante carga)
│   │   ├── mar-bascunana.jpg         # Foto de la socia directora
│   │   ├── vicente.jpg               # Foto del socio
│   │   ├── logo-icao.png             # Logo asociación ICAO
│   │   ├── logo-APAFCV.webp          # Logo asociación APAFCV
│   │   ├── logo-aaedi.png            # Logo asociación AAEDI
│   │   └── logo-api.png              # Logo asociación API
│   └── logo/
│       └── logo-sol-4.png            # Logotipo principal
├── DESIGN_SYSTEM.md                  # Tokens de diseño, tipografía, colores, espaciado
└── README.md
```

---

## Desarrollo local

No hay build ni dependencias. Abre el proyecto directamente con cualquier servidor HTTP local:

```bash
# Opción 1 — VS Code Live Server (extensión recomendada)
# Click derecho en pages/home/index.html → "Open with Live Server"

# Opción 2 — Python
python3 -m http.server 8080
# → http://localhost:8080/pages/home/

# Opción 3 — Node (npx)
npx serve .
```

> No abrir `index.html` como `file://` — los paths relativos de assets funcionan mejor con servidor HTTP.

---

## Secciones de la home

| # | ID | Contenido |
|---|-----|-----------|
| 01 | `#hero` | Hero con video de fondo, titular y CTAs |
| 02 | `#value` | Propuesta de valor — filosofía del despacho |
| 03 | `#services` | Tres servicios principales (compraventa, herencias, testamentos) |
| 04 | `#partners` | Perfiles de Mar Bascuñana y A. Vicente Sáez |
| 05 | `#methodology` | Proceso en 4 pasos |
| 06 | `#testimonials` | Reseñas de Google |
| 07 | `#ecosystem` | Servicios complementarios (bento grid) |
| 08 | `#associations` | Logos de colegios y asociaciones |
| 09 | `#contact` | Formulario de contacto + mapa |

---

## Video del hero

El video de fondo tiene dos versiones optimizadas. El navegador elige automáticamente:

| Archivo | Formato | Tamaño | Compatibilidad |
|---------|---------|--------|---------------|
| `hero-opt.webm` | VP9 | 768 KB | Chrome, Firefox, Edge |
| `hero-opt.mp4` | H.264 | 2.3 MB | Safari + fallback universal |

El original (`hero.mp4`, 38 MB, 1080p 60fps) está en el repo solo como referencia. Si el video se reemplaza, recomprimir con:

```bash
# MP4
ffmpeg -i nuevo.mp4 -vf "scale=1280:-2,fps=30" -c:v libx264 -crf 26 \
  -preset slow -an -movflags +faststart -pix_fmt yuv420p assets/video/hero-opt.mp4 -y

# WebM
ffmpeg -i nuevo.mp4 -vf "scale=1280:-2,fps=30" -c:v libvpx-vp9 \
  -crf 33 -b:v 0 -an assets/video/hero-opt.webm -y

# Poster
ffmpeg -ss 0.5 -i nuevo.mp4 -vframes 1 -vf "scale=1280:-2" \
  -q:v 3 assets/images/hero-poster.jpg -y
```

---

## Sistema de diseño

Documentado en [DESIGN_SYSTEM.md](DESIGN_SYSTEM.md). Resumen:

- **Color primario:** Lila `#7E4DB3` (`--lila-500`)
- **Tipografía heading:** DM Sans 700
- **Tipografía body:** Inter 400/500/600
- **Brand mantra:** *Authority without distance. Closeness without informality.*
- **Idiomas:** Español · English · Deutsch

---

## Repositorio

`git@github.com:rankingonline/sol-4-web.git`  
Rama principal: `main`
