# Explori visuals

Hand-built, self-contained interactive visuals embedded on explori.com, served by GitHub Pages.

## ConEx report page (explori.com/conex)

| Visual | Placement | URL |
|---|---|---|
| From selling space to curating outcomes | Chapter 2 | https://luke3xplori.github.io/explori-visuals/conex/space-to-outcomes.html |
| What it costs to get in the room | Chapter 3 | https://luke3xplori.github.io/explori-visuals/conex/pass-prices.html |
| Nine voices, three audiences, one standard | In conclusion | https://luke3xplori.github.io/explori-visuals/conex/three-lenses.html |

## Embedding

Each visual is a single HTML file with no dependencies beyond Google Fonts. Embed it in an iframe at full width:

```html
<iframe src="https://luke3xplori.github.io/explori-visuals/conex/pass-prices.html"
        title="What it costs to get in the room" loading="lazy"
        style="width:100%;border:0;display:block;height:720px"></iframe>
```

Each visual reports its own height so the host page can size the frame without scrollbars:

```js
window.addEventListener('message', (e) => {
  const d = e.data;
  if (!d || d.source !== 'conex-visual' || e.origin !== 'https://luke3xplori.github.io') return;
  document.querySelectorAll('iframe[src*="/' + d.id + '.html"]').forEach(f => { f.style.height = (d.height + 4) + 'px'; });
});
```

Animations start when the visual scrolls into view and respect prefers-reduced-motion.

## Editing

Edit the HTML file in this repo and commit. GitHub Pages republishes within a minute or two, and the live site picks up the change with no rebuild.
