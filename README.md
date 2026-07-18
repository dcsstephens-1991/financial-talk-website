# Dinero y Cultura (placeholder name)

A modern, bilingual personal-brand site for financial coaching rooted in
Latina culture. Static HTML/CSS/JS — no build step, no framework, works
anywhere (GitHub Pages, Netlify, any static host, or just double-click
`index.html`).

## Preview locally

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Structure

```
index.html, about.html, services.html, contact.html
css/style.css        — all styling, theme via CSS custom properties
js/config.js          — site name, default language, color palettes
js/translations.js    — all English/Spanish copy
js/i18n.js             — language-switching engine
js/theme.js            — color-palette-switching engine
js/main.js              — nav, scroll reveal, parallax, wiring
assets/images/           — photos (see Images below)
```

## Customize

**Brand name** — "The Financial Talk" (search/replace across all `.html`
files and `js/config.js`'s `siteName` if it changes), with an "FT"
monogram in the `.logo-mark` spans / favicon data-URI.

**Copy** — everything is in `js/translations.js`. Every string is
duplicated under `en` and `es`; edit both to keep languages in sync. The
About page bio is Nathaly's real story; the three home-page testimonials
still use realistic-but-placeholder names (Daniela R., Vanessa M., Camila
T.) and invented quotes — swap in real client testimonials (with their
permission) when available. There's no contact email yet — the contact
page currently points people to Instagram/TikTok only; add a real email
or booking link in `contact.card.body`/the contact page once you have
one.

**Default language** — set `defaultLanguage` in `js/config.js` to `"es"`
when Spanish should be the default. A visitor's choice is remembered
(localStorage) and overrides the default on repeat visits.

**Add a language** — add a new top-level key (e.g. `fr`) to
`TRANSLATIONS` in `js/translations.js` with every string translated, then
add `"fr"` to `SITE_CONFIG.supportedLanguages` in `js/config.js`. It will
automatically get a switcher button — add `<button data-lang-option="fr">FR</button>`
next to the EN/ES buttons in each page's `.lang-switcher`.

**Colors** — four palettes ship by default. `midnight-plum-gold` (Midnight
#1C1035, Deep Plum #2A1A4E, Violet #5C3FA0, Soft Gold #E8C97A, Body Plum
#4A3F6B for muted text) is the real brand palette and the default theme;
Fuchsia & Gold, Terracotta & Turquoise, and Violet & Coral are alternates.
Switchable live via the swatch picker in the header. Add more by adding
an entry to the `THEMES` array in `js/config.js` — it appears in the
picker automatically. Each theme is just a set of CSS custom property
overrides.

**Images** — `assets/images/home-about.jpg` and `assets/images/about-story.jpg`
are the two photos currently used, cropped to fill the "blob" shapes
(`.blob-frame`) on the home and about pages. Three more portraits are in
`assets/images/` (`extra-purple-standing.jpg`, `extra-black-tan-bg.jpg`,
`extra-money-throw.jpg`) but not placed on any page yet — swap them in or
add new `<img>`s where useful. Each photo's alt text is a translation key
(e.g. `home.about.photoAlt` in `js/translations.js`) — update it to
describe the actual photo/person once you know who's featured.

**Contact form / booking** — `contact.html` currently only has a mailto
link and social icons (no working form, since there's no backend). Wire
up a real booking link (Calendly, etc.) or a form service (Formspree,
etc.) when ready.

**Social links** — the `#` placeholders in the footer and contact page
social icons need real URLs.
