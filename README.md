# Dinero y Cultura (placeholder name)

A modern, bilingual personal-brand site for financial coaching rooted in
Latina culture. Static HTML/CSS/JS — no build step, no framework, works
anywhere (GitHub Pages, Netlify, any static host, or just double-click
`index.html`).

## Preview locally

```
cd website
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Structure

```
website/
  index.html, about.html, services.html, contact.html
  css/style.css        — all styling, theme via CSS custom properties
  js/config.js          — site name, default language, color palettes
  js/translations.js    — all English/Spanish copy
  js/i18n.js             — language-switching engine
  js/theme.js            — color-palette-switching engine
  js/main.js              — nav, scroll reveal, wiring
```

## Customize

**Brand name** — replace "Dinero y Cultura" (search/replace across all
`.html` files and `js/config.js`'s `siteName`), and swap the "DC" monogram
in the `.logo-mark` spans / favicon data-URI.

**Copy** — everything is in `js/translations.js`. Every string is
duplicated under `en` and `es`; edit both to keep languages in sync. All
current copy is placeholder/sample content (fake testimonials, a stand-in
founder story, `hello@example.com`) — replace before launch.

**Default language** — set `defaultLanguage` in `js/config.js` to `"es"`
when Spanish should be the default. A visitor's choice is remembered
(localStorage) and overrides the default on repeat visits.

**Add a language** — add a new top-level key (e.g. `fr`) to
`TRANSLATIONS` in `js/translations.js` with every string translated, then
add `"fr"` to `SITE_CONFIG.supportedLanguages` in `js/config.js`. It will
automatically get a switcher button — add `<button data-lang-option="fr">FR</button>`
next to the EN/ES buttons in each page's `.lang-switcher`.

**Colors** — three palettes ship by default (Fuchsia & Gold, Terracotta &
Turquoise, Violet & Coral), switchable live via the swatch picker in the
header. Add more by adding an entry to the `THEMES` array in
`js/config.js` — it appears in the picker automatically. Each theme is
just a set of CSS custom property overrides.

**Images** — there are no real photos; the gradient "blob" shapes are
CSS/placeholder stand-ins (`.blob-frame`). Replace with an `<img>` inside
once real photos exist.

**Contact form / booking** — `contact.html` currently only has a mailto
link and social icons (no working form, since there's no backend). Wire
up a real booking link (Calendly, etc.) or a form service (Formspree,
etc.) when ready.

**Social links** — the `#` placeholders in the footer and contact page
social icons need real URLs.
