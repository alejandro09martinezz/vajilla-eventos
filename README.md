# Vajilla Para Eventos — Sitio Web

Sitio web profesional para **Vajilla Para Eventos**, negocio de alquiler de vajilla para eventos en Buenos Aires, Argentina.

---

## Deploy en Vercel

### Opción A — Desde la CLI de Vercel

```bash
# 1. Instalar Vercel CLI (si no lo tenés)
npm install -g vercel

# 2. Entrar a la carpeta del proyecto
cd vajilla-eventos

# 3. Hacer deploy (la primera vez te pedirá login)
vercel

# 4. Para producción
vercel --prod
```

### Opción B — Desde el dashboard de Vercel (sin CLI)

1. Subí la carpeta `vajilla-eventos/` a un repositorio en GitHub.
2. Entrá a [vercel.com](https://vercel.com) y hacé clic en **"Add New Project"**.
3. Importá el repositorio de GitHub.
4. Vercel detecta automáticamente que es un sitio estático. Dejá toda la configuración por defecto.
5. Hacé clic en **"Deploy"**.
6. El sitio queda publicado en `https://vajilla-eventos.vercel.app` (o el nombre que elijas).

### Opción C — Arrastrar y soltar

1. Entrá a [vercel.com/new](https://vercel.com/new).
2. Arrastrá la carpeta `vajilla-eventos/` completa al área de deploy.
3. Listo.

---

## Qué personalizar antes de publicar

### Información de contacto

Abrí `index.html` y reemplazá los siguientes valores:

| Placeholder | Reemplazar por |
|---|---|
| `XXXX-XXXX` | Número de teléfono real |
| `5491100000000` | Número de WhatsApp con código de país (ej: `5491156781234`) |
| `Dirección del local, Buenos Aires` | Dirección real del negocio |
| `+541100000000` (en `href="tel:..."`) | Número real en formato internacional |

### Imágenes del catálogo

Los 6 ítems del catálogo usan bloques de color como placeholder. Para reemplazarlos con fotos reales:

1. Creá la carpeta `img/` dentro del proyecto.
2. Subí las fotos con los nombres `producto-1.webp` … `producto-6.webp` (formato WebP recomendado para performance).
3. En `index.html`, dentro de cada `<figure class="catalog-item">`, reemplazá el `<div class="catalog-placeholder ...">` por:

```html
<img
  src="img/producto-1.webp"
  alt="Descripción detallada del producto"
  width="560"
  height="420"
  loading="lazy"
/>
```

### Imagen OG (Open Graph / redes sociales)

- Creá la carpeta `img/` y subí una imagen llamada `og-image.jpg` (tamaño recomendado: 1200×630 px).
- Esta imagen aparece cuando el sitio se comparte en WhatsApp, Instagram, Facebook, etc.

### Mapa de Google

En `index.html`, buscá el `<iframe>` dentro de `<div class="map-container">` y reemplazá el `src` por el embed real de tu dirección:

1. Buscá la dirección en [Google Maps](https://maps.google.com).
2. Hacé clic en **Compartir → Insertar un mapa**.
3. Copiá la URL del `src` del iframe que te da Google.
4. Pegala en el `src` del iframe en `index.html`.

### Formulario de contacto

El formulario usa [Formspree](https://formspree.io) con el endpoint `xojroeyj`.  
Para usar tu propio endpoint:

1. Creá una cuenta en [formspree.io](https://formspree.io).
2. Creá un nuevo formulario y copiá tu endpoint (ej: `https://formspree.io/f/abcdefgh`).
3. Reemplazá el `action` del `<form>` en `index.html`.

### Textos y estadísticas del Hero

En `index.html`, sección `<!-- HERO -->`, ajustá:

- Los números de las estadísticas (`10+`, `2000+`, `5000+`) según la realidad del negocio.
- El texto descriptivo de la bajada del H1.

### Schema.org / SEO

En el bloque `<script type="application/ld+json">` en `index.html`, completá:

- `"telephone"` con el número real.
- `"streetAddress"` con la dirección real.
- `"sameAs"` con los perfiles de redes sociales reales.

### Canonical y URLs

Buscá todas las ocurrencias de `https://vajilla-eventos.vercel.app` y reemplazalas por el dominio definitivo (ej: `https://vajillaparaeventos.com.ar`) una vez que hayas configurado el dominio en Vercel.

---

## Estructura de archivos

```
vajilla-eventos/
├── index.html          # Página principal
├── css/
│   └── styles.css      # Todos los estilos
├── img/                # (crear) Fotos del catálogo + og-image.jpg
└── README.md           # Este archivo
```

---

## Tecnologías utilizadas

- HTML5 semántico con atributos de accesibilidad ARIA
- CSS3 con variables custom properties, Grid y Flexbox
- Google Fonts: Playfair Display + Inter
- Formspree para el formulario de contacto
- Schema.org JSON-LD para SEO local
- Sin frameworks JS — vanilla JS mínimo para el menú móvil

---

## Puntaje Lighthouse esperado

| Categoría | Puntaje esperado |
|---|---|
| Performance | 90–100 |
| Accessibility | 95–100 |
| Best Practices | 95–100 |
| SEO | 95–100 |
