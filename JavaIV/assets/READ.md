# Java IV — Festivali që përshtatet në çdo ekran

## Çfarë realizova

- Faqe programi për një festival shkencor, e ndërtuar **mobile-first** vetëm me HTML dhe CSS.
- **Menu fleksibile** me Flexbox (`display: flex; flex-wrap: wrap`): në telefon lidhjet kalojnë në rresht të ri, në ekran të gjerë qëndrojnë në një rresht.
- **Gjashtë karta aktivitetesh**. Secila ka kategori, titull, orar (`<time>`) dhe lidhje „Detajet” që të çon te seksioni i detajeve.
- **Grid** për kartat:
  - nën 600 px → 1 kolonë (`grid-template-columns: 1fr`)
  - 600–899 px → 2 kolona (`@media (min-width: 600px)`)
  - nga 900 px → 3 kolona (`@media (min-width: 900px)`)
- **Imazh fleksibël** lokal (`assets/festivali.svg`) me `max-width: 100%; height: auto`.
- **Pa lartësi fikse** për tekstin: kartat rriten sipas përmbajtjes, dhe lidhja „Detajet” shtyhet në fund me `margin-top: auto`.
- Teksti i gjatë nuk del jashtë kartës: `overflow-wrap: anywhere` te titujt dhe `minmax(0, 1fr)` te kolonat e Grid-it.
- Qasshmëri: lidhja „Kalo te përmbajtja”, `aria-label` te menuja, fokus i dukshëm (`:focus-visible`) dhe tekst shtesë për lexuesit e ekranit te lidhjet „Detajet”.

### Sfida e transferimit

Karta „Biologji” ka një titull me **saktësisht 100 karaktere**. Karta „Fizikë” ka një titull të gjatë pa hapësira. Në të dy rastet titulli thyhet brenda kartës dhe karta nuk prishet.


## Testet (hyrje → rezultat i pritur → rezultat i marrë)

Testet u bënë në Chrome DevTools (Device toolbar).

| # | Hyrja | Rezultati i pritur | Rezultati i marrë |
|---|-------|--------------------|-------------------|
| 1 | Gjerësia 360 px | 1 kolonë kartash | 1 kolonë  |
| 2 | Gjerësia 768 px | 2 kolona kartash | 2 kolona  |
| 3 | Gjerësia 1280 px | 3 kolona kartash | 3 kolona  |
| 4 | 360 / 768 / 1280 px: lëviz faqen anash | Pa scroll horizontal | Nuk ka scroll horizontal  |
| 5 | Titull 100-karakterësh dhe titull pa hapësira | Teksti thyhet brenda kartës | Teksti mbetet brenda kartës |
| 6 | Tastiera: Tab disa herë | Fokusi kalon: „Kalo te përmbajtja” → Programi → Detajet → Vendi → Rreth festivalit, me kornizë të dukshme | Rendi siç pritej ✅ |
| 7 | Tastiera: Enter mbi „Rreth festivalit” | Faqja zbret te seksioni „Rreth festivalit” | Funksionon  |
| 8 | Klik ose Enter mbi „Detajet” të një karte | Kalon te përshkrimi përkatës, i theksuar me ngjyrë | Funksionon  |

## Reflektim individual: kur Flexbox, kur Grid?

**Flexbox** e zgjedh kur elementet rreshtohen në **një drejtim** (rresht ose kolonë) dhe madhësia e tyre varet nga përmbajtja. Shembuj: menuja, ku lidhjet kanë gjatësi të ndryshme dhe kalojnë në rresht të ri kur s'ka vend, ose brendia e një karte (kategori → titull → orar → lidhje), ku dua që lidhja të shtyhet në fund.

**Grid** e zgjedh kur dua të kontrolloj **dy dimensione njëherësh**, pra rreshta dhe kolona, dhe numri i kolonave duhet të jetë i saktë. Te kartat kërkesa ishte pikërisht 1/2/3 kolona në pikëndarje të caktuara. Me Grid kjo është një rresht kodi për çdo media query, dhe kartat në të njëjtin rresht marrin automatikisht të njëjtën lartësi.

Pra: **Grid për strukturën e rrjetës, Flexbox për përbërësit brenda saj.** Në këtë projekt i përdora të dyja bashkë.

## Deklarimi i AI dhe burimeve

- Kodi u përgatit me ndihmën e asistentit AI **Claude (Anthropic)**, mbi bazën e skedarëve fillestarë të ushtrimit. E lexova dhe e kuptova çdo pjesë para dorëzimit.
- Imazhi `assets/festivali.svg` është vizatim i thjeshtë origjinal në SVG. Nuk u përdorën asete të jashtme.
- Burime referimi: MDN Web Docs (CSS Grid, Flexbox, Media queries, `overflow-wrap`) dhe kap. 6–7 të librit të lëndës.
- Të dhënat e festivalit janë të sajuara.
