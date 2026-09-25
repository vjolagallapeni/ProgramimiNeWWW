# Java I — Pasaporta digjitale dhe GitHub

## Çfarë realizova

Krijova një pasaportë digjitale për një personazh të sajuar që kandidon si udhërrëfyes i kampusit.

Projekti përmban:
- një faqe kryesore `index.html`;
- një faqe `rreth.html`;
- një listë me 3 aftësi;
- lidhje relative vajtje-kthim mes dy faqeve;
- stilim bazë me `style.css`.

Gjithashtu u krijua struktura e folderëve nga `JavaI` deri te `JavaXIV`.

## Si hapet projekti

1. Hap repository-n `ProgramimiNeWWW` në VS Code.
2. Hape folderin `JavaI`.
3. Hape `index.html` me Live Server.
4. Në faqen kryesore kliko "Lexo më shumë rreth meje" për të hapur `rreth.html`.
5. Nga `rreth.html` kliko "Kthehu te pasaporta" për t'u kthyer te `index.html`.

## Testet

### Testi 1 — Hapja e faqes kryesore

**Hyrja:**  
`index.html` i hapur përmes Live Server.

**Rezultati i pritur:**  
Faqja duhet të hapet dhe të shfaqë titullin "Pasaporta Digjitale", përshkrimin dhe listën me 3 aftësi.

**Rezultati i marrë:**  
Faqja u hap me sukses dhe përmbajtja u shfaq siç ishte planifikuar.

### Testi 2 — Lidhja me rreth.html

**Hyrja:**  
Klikimi në lidhjen "Lexo më shumë rreth meje".

**Rezultati i pritur:**  
Duhet të hapet `rreth.html` pa gabim 404.

**Rezultati i marrë:**  
`rreth.html` u hap me sukses.

### Testi 3 — Lidhja për kthim

**Hyrja:**  
Klikimi në lidhjen "Kthehu te pasaporta".

**Rezultati i pritur:**  
Duhet të kthehet te `index.html` pa gabim 404.

**Rezultati i marrë:**  
Kthimi te `index.html` funksionoi me sukses.

## DevTools — Network

Faqja u testua përmes serverit lokal me DevTools → Network.

**URL:** `http://127.0.0.1:5500/JavaI/index.html`

**Method:** GET

**Status:** 304 Not Modified

## Reflektim individual

### Cili ndryshim është ruajtur lokalisht por ende nuk shihet në GitHub?

Një ndryshim i ruajtur lokalisht, por që ende nuk shihet në GitHub, është çdo ndryshim që nuk është bërë commit dhe push. Për shembull, `README.md` mund të jetë i ruajtur në kompjuter, por nuk shfaqet në GitHub derisa të bëhet commit dhe push.

## AI dhe burimet

Për realizimin e detyrës është përdorur AI për orientim dhe shpjegim të koncepteve të HTML, Git dhe GitHub. Përmbajtja dhe struktura e projektit janë përshtatur dhe kontrolluar gjatë punës.

Burimi tematik: *Fundamentals of Web Development*, Randy Connolly dhe Ricardo Hoar, kapitujt 1–3.