# Pendientes antes de invertir pauta

Estos datos venían en el HTML original pero **no están respaldados en tucasafacil.cl** (revisado el 08-09-2026). No se publicaron inventados. Confírmame cada uno y los cierro.

## 1. Cifras del hero

Hoy el hero muestra tres datos verificables: `114 mm` (muro Panel SIP), `−50%` (tiempo de obra) y `48 cuotas`.

El HTML original traía `90 días de fabricación`, `100% precio cerrado` y `+200 proyectos`. Ninguno figura publicado.

| Dato | Qué necesito | Riesgo si se publica sin respaldo |
|---|---|---|
| 90 días de fabricación | Plazo contractual promedio real, por modelo o rango | Es una promesa de plazo. Si el vendedor no la sostiene, el lead se cae en la primera reunión |
| +200 proyectos | N.º de casas entregadas y desde qué año | Ley 19.496 sobre publicidad: una cifra de respaldo debe ser demostrable |
| 100% precio cerrado | Cláusula del contrato que lo fija | Es la objeción #2 del comprador. Sostenerla vale más que cualquier otro mensaje |

En `index.html` hay un bloque comentado listo para reemplazar en cuanto los confirmes (busca `PENDIENTE`).

## 2. Dormitorios y baños de los cuatro modelos

Aparecen en la página como un chip ámbar visible: `◆ dorm. y baños por confirmar`. Es intencional — así no se te pasa. **Quítalos antes de publicar** o pásame los números.

| Modelo | Superficie | Dormitorios | Baños |
|---|---|---|---|
| Llanquihue | 218 m² | ? | ? |
| Borde Lago | 130 m² | ? | ? |
| Villa Costera | 88 m² | ? | ? |
| Refugio | 50 m² | ? | ? |

## 3. Asignación de fotos a modelos

Asigné las cuatro fotos por superficie (la más grande y de dos pisos → Llanquihue 218; la de un piso extendido → Borde Lago 130; la de terraza cubierta → Villa Costera 88; el volumen compacto → Refugio 50). **Confírmame que quedaron bien pareadas**, porque la descripción de cada tarjeta describe lo que se ve en su foto.

## 4. Datos corregidos respecto del HTML original

Ya los cambié, para que sepas qué se movió:

- El pie decía «Showrooms: Llanquihue 218 · Borde Lago 130». Esos son **modelos**, no direcciones. Ahora dice San Bernardo (RM) y Llanquihue (Los Lagos).
- El paso 2 invitaba «a Llanquihue o Borde Lago» como si fueran sedes. Corregido.
- «Termopanel de serie» y «certificación energética» no están publicados: eliminados.
- «Accesibilidad universal» quedó como «un solo nivel, sin escaleras y con acceso a nivel de terreno», que es lo que se ve en la foto y no requiere certificación.
- © 2024 → © 2026.
- Las fotos de Unsplash (casas que no son tuyas) salieron. Se usan tus cuatro fotos, alojadas en el repo.

## 5. Técnicos

- [ ] Dominio definitivo → reemplazar `terreno.tucasafacil.cl` en `index.html`, `robots.txt` y `sitemap.xml`.
- [ ] ID del Meta Pixel → descomentar el bloque del `<head>`.
- [ ] En GA4: marcar `generate_lead` como conversión; crear dimensiones personalizadas `cta_ubicacion` y `variante`.
- [ ] En la landing de showroom: agregar `variante: 'showroom'` a sus eventos, o el A/B no se podrá comparar en el mismo informe.
- [ ] Revisar que el formulario de HubSpot (portal 9292440) tenga los campos **comuna del terreno**, **superficie** y **modelo de interés**. Sin ellos, el lead llega sin lo que el asesor necesita para la reunión de factibilidad.

## Sugerencia sobre el test A/B

Dos landings compitiendo necesitan tráfico separado y suficiente. Con menos de ~100 conversiones por variante el resultado no es concluyente. Antes de partir, define:

- **Métrica de decisión:** leads / sesiones (no clics en CTA).
- **Reparto:** dos campañas o dos conjuntos de anuncios distintos, mismo presupuesto, mismos públicos y creatividades.
- **Duración mínima:** dos semanas completas, para no leer un sesgo de día de semana.
- **Métrica de calidad:** show-rate de la visita agendada. Una landing puede ganar en volumen de leads y perder en visitas efectivas — y esa es la que importa.
