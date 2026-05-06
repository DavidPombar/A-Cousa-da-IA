# A Cousa da IA — Landing do obradoiro

Landing page estática para o obradoiro **"Do prompt ao sistema · Enxeñería de
software con LLMs"**.

> Sitio: [https://davidpombar.github.io/A-Cousa-da-IA/](https://davidpombar.github.io/A-Cousa-da-IA/)

---

## Stack

Sen dependencias, sen build, sen frameworks.

- **HTML estático** (`index.html`)
- **CSS feito a man** (`styles.css`) con design tokens via CSS custom properties
- **Tipografía**: Geist Sans + Geist Mono desde Google Fonts
- **Hosting**: GitHub Pages (rama `main`, raíz)
- **Inscricións**: Eventbrite (botóns externos, sen formulario propio)
- **Idioma**: Galego (`lang="gl"`)
- **Tema**: Escuro · estilo Vercel/Linear

---

## Estrutura do repositorio

```text
.
├── index.html           # toda a landing nun único ficheiro
├── styles.css           # ~600 liñas con design tokens
├── favicon.svg          # icona simple (cadrado branco con "/")
├── .nojekyll            # evita o procesado por Jekyll en GitHub Pages
├── assets/
│   ├── instructors/     # fotos dos instrutores (cadradas, >= 400x400 px)
│   │   └── iago-lastra.png
│   └── logos/
│       ├── README.md            # como engadir os logos
│       ├── startup-galicia.jpg  # logo do organizador
│       └── colaboradores/       # (vacío de momento)
└── README.md            # este ficheiro
```

---

## Como traballar localmente

Non hai build. Abre `index.html` no navegador ou serve a carpeta cun servidor
estático calquera:

```bash
# Opción 1: Python
python3 -m http.server 8000

# Opción 2: Node (npx, sen instalar nada)
npx --yes serve .

# Opción 3: simplemente abre index.html no navegador
open index.html
```

Despois visita `http://localhost:8000`.

---

## Como despregar en GitHub Pages

Unha vez fusionado o PR a `main`:

1. Vai a **Settings → Pages** no repositorio.
2. En **Source** selecciona `Deploy from a branch`.
3. Branch: `main`, carpeta: `/ (root)`. Garda.
4. En 1-2 minutos a páxina estará dispoñible en
   `https://davidpombar.github.io/A-Cousa-da-IA/`.

Cada `push` a `main` redespregará automáticamente.

---

## Tarefas pendentes (placeholders no código)

| # | Onde | Que substituír |
|---|---|---|
| 1 | `index.html` · sección 07 (Instrutores) | Engadir máis instrutores se procede (Iago Lastra xa engadido). |
| 2 | ~~`index.html` · sección 08 (Organizado por)~~ | ✅ Startup Galicia engadido. |
| 3 | ~~`index.html` · sección 09 (Colaboradores)~~ | ✅ Hi, Docuten e Marosa engadidos. |
| 4 | `index.html` · sección 06 (Datas) | Cando se confirme Vigo, actualizar data e ubicación. |
| 5 | `index.html` · meta `og:image` | Engadir imaxe para redes sociais (1200×630 px). |

Para os puntos 2 e 3, le `assets/logos/README.md` para as instrucións detalladas.

---

## Convencións de edición

### Cambiar copys

Toda a copy está en `index.html`. Está organizada en seccións con comentarios
claros (`<!-- ============... -->`). Edita o texto entre etiquetas, garda e
recarga.

### Cambiar cores ou tipografía

Todo está parametrizado en `:root` ao inicio de `styles.css`:

```css
:root {
  --bg: #0a0a0a;
  --text: #ededed;
  --accent: #ffffff;
  /* ... */
}
```

Cambia un valor e afectará a toda a landing.

### Cambiar a versión clara

Se algún día queres pasar a tema claro, substitúe os tokens de `:root` polos da
sección "Opción B — Light" da especificación orixinal e listo.

---

## Accesibilidade

- `lang="gl"` no `<html>`.
- Estrutura semántica (`<header>`, `<main>`, `<section>`, `<footer>`, `<nav>`).
- Skip-link ao principio do `<body>`.
- Estilos `:focus-visible` claramente diferenciables.
- Soporte para `prefers-reduced-motion`.
- Contraste alto (texto branco sobre fondo case-negro).

---

## Roadmap suxerido

- [ ] Engadir os logos reais (organizador + colaboradores).
- [ ] Substituír a bio do instrutor.
- [ ] Crear unha imaxe `og-image.png` (1200×630) e ligala no `<head>`.
- [ ] Confirmar data e lugar de Vigo e actualizar a sección "Datas".
- [ ] Engadir unha sección de testimonios cando estea dispoñible feedback de
      edicións anteriores.

---

## Licenza

Código baixo licenza MIT. Os contidos (textos, deseño da axenda, materiais do
obradoiro) son propiedade dos organizadores.
