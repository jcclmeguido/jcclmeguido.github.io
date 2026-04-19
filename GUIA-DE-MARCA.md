# Guía de marca — J2CL

**Proyectos y Servicios · Diseño · Desarrollo · Consultoría**

---

## 1. Identidad visual

### Color principal
| Uso | HEX | RGB |
|-----|-----|-----|
| **Verde bosque** (fondo del badge, texto sobre blanco) | `#1A3A2E` | `26, 58, 46` |
| **Blanco** (letras sobre el badge, texto sobre oscuro) | `#FFFFFF` | `255, 255, 255` |

Un solo color de marca. Si necesitas un acento (botones, links, highlights), usa una versión más clara del mismo verde: `#2D5943` o `#4A8A6E`. Nunca un segundo color saturado.

### Tipografía
Sans-serif geométrico con peso medio. Para documentos y web, usa **Inter** (gratis en Google Fonts).

```css
font-family: "Inter", "Helvetica Neue", Arial, sans-serif;
```

---

## 2. Versiones disponibles

| Archivo | Cuándo usarlo |
|---------|---------------|
| `j2cl-logo-badge.svg` | Logo principal. 9 de cada 10 casos. |
| `j2cl-logo-horizontal.svg` | Lockup completo sobre **fondo claro** (documentos, propuestas, letterhead). |
| `j2cl-logo-horizontal-oscuro.svg` | Lockup completo sobre **fondo oscuro** (web en dark mode, videos, presentaciones). |
| `j2cl-logo-inverso.svg` | Badge con fondo blanco y letras verdes. Para contextos donde el verde no funciona. |
| `j2cl-logo-outline.svg` | Marcas de agua, sellos, aplicaciones sutiles. |
| `favicon.ico` | Pestaña del navegador en tu sitio web. |
| `j2cl-logo-badge-{16..1024}.png` | PNGs para sistemas que no aceptan SVG (WhatsApp, sellos legacy). |

### Regla de oro para elegir versión
**Mira el fondo y elige la versión cuyo texto contraste más:**
- Fondo claro (blanco, gris claro, papel) → usa `j2cl-logo-horizontal.svg` (texto verde)
- Fondo oscuro (negro, gris oscuro, dark mode) → usa `j2cl-logo-horizontal-oscuro.svg` (texto blanco)
- El badge en sí **siempre se queda igual** (verde con letras blancas): funciona en ambos mundos.

---

## 3. Reglas de uso

**Área de respeto.** Deja al menos ½ de la altura del badge como margen libre alrededor.

**Tamaño mínimo.** No uses el badge por debajo de 28×28 px en pantalla ni 10mm impreso (por el layout 2×2, necesita un poco más de espacio que un monograma simple).

**Qué SÍ hacer:**
- Usarlo sobre blanco, gris claro o fondos muy oscuros (con la versión correspondiente)
- Mantener siempre la proporción cuadrada del badge
- Respetar la separación entre las dos líneas `j2` y `cl`
- Elegir la versión del lockup según el contraste del fondo

**Qué NO hacer:**
- ❌ Estirar, inclinar o rotar el badge
- ❌ Cambiar los colores (verde bosque o blanco, nada más)
- ❌ Agregar sombras, degradados, contornos decorativos
- ❌ Juntar "j2cl" en una sola línea (rompe el monograma)
- ❌ Usar la versión clara sobre fondo oscuro (el verde se pierde) o viceversa
- ❌ Poner el logo sobre fondos con baja legibilidad o imágenes ocupadas

---

## 4. Código listo para copiar

### Para tu sitio web (HTML)

```html
<link rel="icon" type="image/svg+xml" href="/j2cl-logo-badge.svg">
<link rel="icon" type="image/x-icon" href="/favicon.ico">
<link rel="apple-touch-icon" sizes="180x180" href="/j2cl-logo-badge-256.png">

<a href="/" class="logo">
  <img src="/j2cl-logo-badge.svg" alt="J2CL" width="48" height="48">
</a>
```

### Cambio automático de logo según dark mode

Si tu sitio soporta modo oscuro, puedes cambiar el lockup automáticamente:

```html
<picture>
  <source srcset="/j2cl-logo-horizontal-oscuro.svg" media="(prefers-color-scheme: dark)">
  <img src="/j2cl-logo-horizontal.svg" alt="J2CL — Diseño, Desarrollo, Consultoría" height="60">
</picture>
```

### Para tu firma de email

Como los correos se ven normalmente sobre fondo blanco, usa la versión clara:

```html
<table cellpadding="0" cellspacing="0" border="0">
  <tr>
    <td style="padding-right:16px; vertical-align:middle;">
      <img src="CDN_URL/j2cl-logo-badge-128.png" width="64" height="64" alt="J2CL">
    </td>
    <td style="vertical-align:middle; font-family:Inter,Arial,sans-serif;">
      <div style="font-size:18px; font-weight:600; color:#1A3A2E; letter-spacing:-0.5px;">J2CL</div>
      <div style="font-size:12px; color:#1A3A2E; opacity:0.75; letter-spacing:1px;">DISEÑO · DESARROLLO · CONSULTORÍA</div>
      <div style="font-size:13px; color:#1A3A2E; margin-top:6px;">Julio Cesar Campos</div>
      <div style="font-size:12px; color:#666;">Santa Cruz, Bolivia · tu@email.com</div>
    </td>
  </tr>
</table>
```

### Para ASP.NET Razor

```razor
<link rel="icon" type="image/svg+xml" href="~/images/j2cl-logo-badge.svg" />
<link rel="icon" type="image/x-icon" href="~/favicon.ico" />

<a class="navbar-brand d-flex align-items-center" asp-controller="Home" asp-action="Index">
    <img src="~/images/j2cl-logo-badge.svg" alt="J2CL" height="40" class="me-2" />
    <span style="color:#1A3A2E; font-weight:500; letter-spacing:-0.5px;">J2CL</span>
</a>
```

### Para tus proyectos en Bootstrap 5

```css
:root {
  --j2cl-brand: #1A3A2E;
  --j2cl-brand-soft: #2D5943;
  --j2cl-brand-light: #4A8A6E;
}

.btn-j2cl {
  background-color: var(--j2cl-brand);
  color: #fff;
  border: none;
}
.btn-j2cl:hover {
  background-color: var(--j2cl-brand-soft);
  color: #fff;
}
.text-j2cl { color: var(--j2cl-brand) !important; }
.bg-j2cl { background-color: var(--j2cl-brand) !important; }
```

---

## 5. Ejemplos de aplicación por contexto

| Contexto | Versión a usar |
|----------|----------------|
| Propuesta comercial en Word/PDF | `j2cl-logo-horizontal.svg` (fondo blanco) |
| Firma de email | Badge + texto HTML en verde sobre fondo blanco |
| Landing page en light mode | `j2cl-logo-horizontal.svg` |
| Landing page en dark mode | `j2cl-logo-horizontal-oscuro.svg` |
| Presentación con slides oscuros | `j2cl-logo-horizontal-oscuro.svg` |
| Presentación con slides blancos | `j2cl-logo-horizontal.svg` |
| Avatar de GitHub / LinkedIn | `j2cl-logo-badge-256.png` |
| Favicon web | `favicon.ico` |
| Tarjeta de presentación (frente) | Badge grande solo |
| Tarjeta de presentación (reverso) | `j2cl-logo-horizontal.svg` o versión oscura según diseño |
| Marca de agua en documentos | `j2cl-logo-outline.svg` |
| Video / reels con fondo oscuro | `j2cl-logo-horizontal-oscuro.svg` |

---

## 6. Siguientes pasos sugeridos

1. **Registra el dominio:** `j2cl.bo`, `j2cl.dev`, o `j2cl.com`.
2. **Reserva @j2cl** en GitHub, LinkedIn, Instagram y donde tengas presencia.
3. **Aplica el badge 256×256** como avatar en GitHub, LinkedIn y tu GitLab en `git.axon.com.bo`.
4. **Actualiza tu plantilla de propuesta comercial** (la que usaste para los Bs 8.500 de SLN_GestionPedidos) reemplazando el encabezado con el `j2cl-logo-horizontal.svg`.
5. **Firma de correo:** implementa el snippet HTML de arriba.

---

*Guía actualizada el 19 de abril de 2026 · J2CL Proyectos y Servicios · versión 2 (añade lockup para fondo oscuro).*
