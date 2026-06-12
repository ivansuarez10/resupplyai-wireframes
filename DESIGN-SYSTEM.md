# ResupplyAI — Design System v1 (definitivo)

Referencia: `04c-dashboard-hybrid.html` es la pantalla canónica. Toda pantalla nueva o actualizada debe seguir este sistema.

## Fundamentos

- **Fuente:** Lato (Google Fonts) — 300/400/700/900. Títulos y números clave en `font-black` (900).
- **Fondo de página:** `#f5f7fc` (claro siempre; no dark mode).
- **Monocromía de marca:** TODO el color de la UI vive en una sola familia:

| Token | Hex | Uso |
|---|---|---|
| `--navy` | `#21325f` | Texto de máxima jerarquía, extremo oscuro de degradados |
| `--primary` | `#2a3d88` | Color principal, links, estados activos |
| azul medio | `#4a63c4` | Blob intermedio del hero |
| azul claro | `#5e7ee8` | Acentos secundarios, scores medios, dots |
| azul pálido | `#9db4ff` / `#aab9f5` | Live dots, texto positivo sobre navy |

- **Prohibido:** verdes, rojos, ámbar como acentos. La urgencia se comunica con **intensidad y peso** (degradado fuerte + font-black = más urgente; opacidad reducida = menos urgente), no con semáforo.
- **Degradado de marca:** `linear-gradient(135deg, #2a3d88, #21325f)` para botones primarios, badges, avatar.

## Superficies

- **Cards flotantes (blancas):** `#fff`, `border-radius: 22px`, sombra `0 24px 60px rgba(33,50,95,0.10), 0 4px 16px rgba(33,50,95,0.05)`. Hover: sube a `0 36px 90px rgba(33,50,95,0.16)` + `translateY(-3px)`.
- **Hero card:** gradiente animado con blobs CSS `@property` (colores `#4a63c4`, `#1a2850`, `#5e7ee8` sobre base `--primary`), sombra profunda `0 32px 80px rgba(33,50,95,0.32)`.
- **Sidebar:** blanco, 200px, sticky, nav items con barra indicadora activa de 3px.
- **Orbes ambientales:** 2 orbes fijos difuminados (`blur(80px)`, `#c7d4f8`/`#dbe4fb`) flotando detrás del contenido.

## Animaciones

- **Entrada:** hero `heroIn 0.7s`, cards en cascada `cardIn 0.6s` con delays escalonados, filas de tabla con stagger desde la izquierda.
- **Datos:** contadores numéricos ease-out 1.4s, score rings SVG (`stroke-dashoffset`), chart de área con línea que se dibuja (`stroke-dasharray`), sparklines que crecen en cascada.
- **Cursor (solo `pointer: fine`):** spotlight que sigue el mouse (blanco en hero, azul 6% en cards blancas), tilt 3D ±6° en cards pequeñas, botones magnéticos, parallax sutil de blobs.
- **Siempre:** respetar `prefers-reduced-motion`.

## Responsive

- Desktop ≥1024px: sidebar sticky visible.
- <1024px: sidebar oculto (hamburger + overlay + Escape), grids a 1 columna, tablas con scroll horizontal.
- Breakpoint tablet 640–1023px: KPIs en 2 columnas.

## Logos

- `logo-normal.png` (R + texto navy) sobre fondos claros.
- `logo-white.png` sobre navy/oscuro (hero, email header).

## Estado de las pantallas

- ✅ `04c-dashboard-hybrid.html` — canónica
- ⏳ Pendientes de migrar a este sistema: 01–03 (auth), 05–07, 09–10 (dashboard), 08 (admin), 11–12, index
