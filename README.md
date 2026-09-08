# Landing "Terreno" · Tu Casa Fácil

Landing de conversión estática. Ángulo: **factibilidad de terreno** → lead por formulario HubSpot.
Es la **variante B** del test A/B contra la landing de showroom (variante A, conversión por WhatsApp).

| | Variante A | Variante B (este repo) |
|---|---|---|
| Ángulo | Camina dentro de tu casa antes de comprarla | Tu terreno ya está listo, la casa la ponemos nosotros |
| CTA | Agenda tu visita | Evaluar mi terreno |
| Conversión | WhatsApp prellenado | Formulario HubSpot |
| Parámetro GA4 | `variante: 'showroom'` | `variante: 'terreno'` |

## Paleta

Derivada del logo. Colores exactos muestreados del archivo original:

| Color | Hex | Uso en la página |
|---|---|---|
| Negro | `#0B0D0C` | CTAs, titulares, sección del formulario. Es el color dominante del logo |
| Verde hoja | `#55B110` | Solo gráfica: números de paso, franjas, bordes, ring de foco. **No** para texto pequeño (2,6:1) |
| Verde texto | `#2F6408` | Acentos tipográficos: frase clave del titular, m² de modelos, regiones (6,9:1, AA) |
| Naranja | `#B85400` | Un solo uso: el badge sobre el titular, replicando el acento del "FÁ" (4,7:1, AA) |
| Magenta `#BF3692` · Azul `#009ACA` | — | **Se quedan dentro del logo.** Cinco colores en la interfaz rompen el posicionamiento premium |

Todo el texto cumple WCAG AA. El logo se usa como archivo real (`assets/logo-tucasafacil.png`, fondo transparente) en header y pie.

## Contenido del repo

```
index.html          Landing completa (HTML + CSS + JS en un archivo)
assets/logo-*.png   Logo con fondo transparente (header y pie)
assets/favicon.png  Favicon: la marca sobre negro, para que la hoja verde se lea en pestañas claras
assets/apple-touch-icon.png · icon-512.png
assets/img/         Fotos optimizadas (webp + jpg, 4:3, 1600px y 900px) + imagen OG
robots.txt
sitemap.xml
vercel.json         Cache de assets + headers de seguridad
PENDIENTES.md       Qué falta confirmar antes de invertir pauta
```

Sin dependencias, sin build. Se sirve tal cual.

## Subir a GitHub (vía web, sin terminal)

1. Entra a [github.com/new](https://github.com/new) → nombre `tcf-landing-terreno` → **Private** → *Create repository*.
2. En el repo vacío: **uploading an existing file**.
3. Arrastra `index.html`, `robots.txt`, `sitemap.xml`, `vercel.json`, `README.md`, `PENDIENTES.md` y **la carpeta `assets` completa** (Chrome respeta la estructura de carpetas al arrastrarla).
4. *Commit changes*.

## Subir con terminal

```bash
cd tcf-landing-terreno
git init -b main
git add .
git commit -m "Landing terreno: variante B del test A/B"
git remote add origin git@github.com:TU-USUARIO/tcf-landing-terreno.git
git push -u origin main
```

## Publicar en Vercel

1. [vercel.com/new](https://vercel.com/new) → *Import Git Repository* → elige el repo.
2. Framework Preset: **Other**. Build Command: vacío. Output Directory: vacío (raíz).
3. *Deploy*. Queda en `tcf-landing-terreno.vercel.app`.
4. *Settings → Domains* → agrega el subdominio definitivo (ej. `terreno.tucasafacil.cl`) y crea el CNAME en tu DNS.
5. **Después de fijar el dominio**, reemplaza `terreno.tucasafacil.cl` en `index.html` (canonical, `og:url`, `og:image`, `twitter:image`), `robots.txt` y `sitemap.xml`.

## Medición

- GA4 `G-J12VB8HEGJ` cargado en el `<head>`.
- Evento `solicitar_factibilidad` en cada clic de CTA, con `cta_ubicacion`: `header · hero · modelos · cierre · sticky · whatsapp_form · whatsapp_footer`.
- Evento `generate_lead` con `cta_ubicacion: form_enviado` al enviar el formulario de HubSpot (escucha `hsFormCallback / onFormSubmitted`). **Esta es la conversión real.**
- Todos los eventos incluyen `variante: 'terreno'`.
- Meta Pixel: bloque comentado en el `<head>`, listo para pegar el ID.

En GA4: marcar `generate_lead` como conversión y crear dimensiones personalizadas para `cta_ubicacion` y `variante`.

## Cómo probar en local

```bash
python3 -m http.server 8000
# abrir http://localhost:8000
```

El formulario de HubSpot solo carga sobre `http://` o `https://`, no abriendo el archivo con doble clic.
