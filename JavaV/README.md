# Java V — Formulari i misionit sekret

Skedarët: `index.html` (formulari + tabela), `pranuar.html` (faqja e demonstrimit), `style.css`.

## Para kodimit

**Hyrjet:** pseudonimi (tekst 3–20 karaktere), email, numri i personave (1–5), kategoria (Art / Shkencë), pranimi i rregullave.

**Daljet:** nëse ka gabim, shfletuesi e ndal dërgimin dhe tregon mesazhin te fusha e parë e gabuar. Nëse gjithçka është valide, hapet `pranuar.html?pseudonimi=…&email=…&persona=…&kategoria=…&rregullat=po`.

**Rast normal:** `Hija7`, `hija7@example.org`, `3`, Shkencë, rregullat të pranuara → kalon te `pranuar.html`.

**Raste kufitare:**
- Persona `1` dhe `5` kalojnë; `0` dhe `6` nuk kalojnë (`min`/`max`).
- Pseudonimi me 2 karaktere nuk kalon (`minlength="3"`); me 3 ose 20 kalon; më shumë se 20 nuk mund të shkruhet (`maxlength="20"`).
- Email `hija7` (pa @) nuk kalon (`type="email"`).

## Rastet e pranimit

- [x] Formulari bosh nuk kalon (`required` në çdo fushë, edhe në radio dhe checkbox).
- [x] Email pa format email-i dhe grup 0 ose 6 nuk kalojnë.
- [x] Të dhënat valide çojnë te `pranuar.html`; tabela ka `caption` dhe tituj kolonash `th scope="col"` (plus `th scope="row"` për orët).


## Reflektim individual

**Pse `required` në frontend nuk provon që të dhënat në një sistem real janë të sigurta?**

Validimi në HTML ekziston për përdoruesin: e njofton menjëherë dhe e ndihmon të plotësojë formularin saktë. Por ai ndodh në shfletuesin e klientit, dhe klienti e kontrollon plotësisht atë. Dikush mund ta heqë `required` me DevTools, ta çaktivizojë validimin (`novalidate`), ta ndryshojë URL-në GET me dorë (p.sh. `persona=99`), ose ta dërgojë kërkesën drejtpërdrejt me `curl` apo Postman pa e hapur fare formularin. Përveç kësaj, `required` kontrollon vetëm formën e të dhënave. Ai nuk tregon nëse email-i ekziston, nëse përdoruesi ka leje, ose nëse teksti përmban kod të dëmshëm (XSS, SQL injection). Në një sistem real serveri duhet t'i validojë përsëri të gjitha të dhënat, t'i pastrojë dhe t'i ruajë në mënyrë të sigurt. Për të dhëna të ndjeshme duhet përdorur POST mbi HTTPS.
