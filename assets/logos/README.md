# Logos

Esta carpeta contén os logos que se usan na landing.

## Estrutura actual

```text
assets/
└── logos/
    ├── startup-galicia.jpg          ← organizador (sección 8)
    └── colaboradores/
        └── (engadir aquí logos)     ← colaboradores (sección 9)
```

## Dous estilos visuais distintos

A landing usa dous estilos visuais para os logos:

| | Organizador | Colaboradores |
|---|---|---|
| **Clase CSS no `<a>`** | `.organizer-logo` | `.collaborator-logo` |
| **Tamaño** | Grande (`max-height: 160px`) | Pequeno (`max-height: 40px`) |
| **Cor** | Mantén os colores orixinais | Convertidos a escala de grises |
| **Hover** | Lixeiro `scale(1.03)` | Aumento de opacidade |

## Como engadir colaboradores

Na sección **"Entidades colaboradoras"** de `index.html`, busca os
`<div class="logo-placeholder">` e substitúeos por:

```html
<a
  class="collaborator-logo"
  href="https://url-da-entidade.example/"
  target="_blank"
  rel="noopener noreferrer"
  aria-label="Nome da entidade"
>
  <img
    src="assets/logos/colaboradores/nome-entidade.svg"
    alt="Nome da entidade"
    width="200"
    height="60"
    loading="lazy"
  />
</a>
```

### Modificador para logos con fondo claro

Se o logo ten **fondo branco ou claro** (texto escuro sobre fondo claro), engade
a clase modificadora `collaborator-logo--invert`:

```html
<a class="collaborator-logo collaborator-logo--invert" ...>
  <img src="..." />
</a>
```

Isto aplica `filter: invert(1)` para que o fondo claro se converta en escuro e
poida fundirse co fondo da páxina, igual que o resto.

| Tipo de logo | Clase a usar |
|---|---|
| Fondo escuro / negro (texto branco) | `collaborator-logo` |
| Fondo claro / branco (texto escuro) | `collaborator-logo collaborator-logo--invert` |
| Fondo transparente (SVG ideal) | calquera das dúas — proba e queda coa que mellor se vexa |

## Recomendacións de formato

- **SVG**: preferido (escalable, lixeiro, mantén nitidez en pantallas Retina).
- **PNG con transparencia**: segunda opción se non tes SVG.
- **JPEG**: evita se podes; non admite transparencia. O caso de Startup Galicia
  funciona porque o seu fondo é case negro e usamos `mix-blend-mode: lighten`
  no CSS para integralo co fondo escuro.

## Truco CSS: `mix-blend-mode`

O logo de Startup Galicia é JPEG con fondo negro. Para que ese rectángulo
negro non sexa visible sobre o noso fondo escuro (`#0a0a0a`), o CSS aplica:

```css
.organizer-logo img {
  mix-blend-mode: lighten;
}
```

Isto fai que o navegador combine cada píxel do logo co fondo da páxina,
elixindo o **máis claro** dos dous. Os píxeles negros do fondo do JPEG
volvénse exactamente da cor do noso fondo (invisibles), mentres que as
cores vivas da espiral e o texto branco se manteñen intactas.
