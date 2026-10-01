# Muzeu i sendeve të zakonshme — Java II

Faqe statike (vetëm front end): HTML + CSS, pa JavaScript.

## Plani para kodimit

- **Hyrjet:** teksti i kartave, tri skedarë SVG (`celesi.svg`, `filxhani.svg`, `bileta.svg`), data e ekspozitës.
- **Daljet:** një faqe me titull, navigim, tri karta (titull, figurë, përshkrim, "Historia e fshehur") dhe footer.
- **Rast normal:** ekran i gjerë, tri kartat në një rresht; klikimi te "Historia e fshehur" hap tekstin.
- **Rast kufitar 1:** ekran i ngushtë (telefon) — kartat bien njëra nën tjetrën, pa lëvizje horizontale.
- **Rast kufitar 2:** figura nuk ngarkohet — teksti `alt` shfaqet dhe faqja mbetet e lexueshme; navigimi me tastierë (Tab) ka fokus të dukshëm.

## Skedarët

- `index.html` — struktura (header, nav, main, footer, `article`, `details`)
- `style.css` — pamja (ngjyrat si variabla, grid për kartat)
- `*.svg` — figurat
