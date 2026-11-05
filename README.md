# Basketbold 🏀

Daglig basketball-træning til iPad: én øvelse om dagen, point, streak, præmier og ugentlig testdag.
Alt ligger i én `index.html` – ingen server, ingen konto. Data gemmes lokalt på iPad'en.

## Udgiv på GitHub Pages (5 minutter)

1. Opret et nyt repo på GitHub, fx `basketbold` (public).
2. Læg alle filerne fra denne mappe i roden af repoet:
   `index.html`, `sw.js`, `manifest.webmanifest`, `icon-180.png`, `icon-192.png`, `icon-512.png`
3. I repoet: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root) → Save**.
4. Efter ca. 1 minut ligger appen på `https://<dit-brugernavn>.github.io/basketbold/`

## Sæt den på iPad'en

1. Åbn adressen i **Safari** på iPad'en.
2. Tryk på del-knappen (firkant med pil) → **Føj til hjemmeskærm** → Tilføj.
3. Åbn appen fra hjemmeskærmen. Så kører den i fuld skærm og virker også uden wifi ude ved kurven.
4. Første gang: skriv barnets navn. Gå i **Mere → Forældre-menu** og sæt præmier, modstandernavn og evt. en PIN.

## Opdatere appen

Ret `index.html`, og skift `CACHE`-navnet øverst i `sw.js` (fx `basketbold-v2`). Commit og push.
Næste gang appen åbnes med netforbindelse, henter den den nye version.

## Backup

Point og historik gemmes kun i den iPad, appen kører på. Brug **Forældre-menu → Gem backup-fil** en gang imellem
(filen havner i Filer/Downloads på iPad'en, eller brug "Kopiér som tekst" og gem i Noter). Gendan med **⬆️ Gendan**.

## Sådan virker spillet

- Barnet er på ét **niveau** ad gangen (1–4) og bliver der, indtil en voksen låser det næste op i *Forældre-menuen*.
- Hvert niveau har 8–12 øvelser med faste mål (fx "50 driblinger med hver hånd", "10 lay-ups fra hver side"). Barnet trykker én gang på "Færdig", når et trin er lavet – appen går selv videre til næste trin.
- **Point:** alle øvelser på niveauet giver tilsammen **25 point om dagen** – kun hvis alle bliver lavet (fx 11 øvelser × 2 point + 3 bonus). Ekstra øvelser, tests og dueller giver ingen point.
- **Præmiestigen:** pointene samler sig op (de bruges ikke). Ved 50, 100, 150 … 1000 point kan en præmie hentes: sodavandsis, sodavand, slik, Cheese Dippers – og Bakken Bears-kamp ved 500 og 1000. Stigen kan ændres i Forældre-menuen.
- **Streak 🔥:** træn hver dag. Én fridag pr. uge er tilladt uden at miste streaken.
- **Testdag (søndag):** 4 faste tests – straffekast af 10, lay-ups af 10, crossovers i træk, mellem benene i træk – med grafer under *Udvikling*.
- **Duel ⚔️:** samme test mod far/mor – kun for æren.
- **Regnvejr ☔:** viser kun indendørs-øvelser.

## Stemme, tegninger og videoer

- **Stemme:** appen læser øvelsen, nedtællingen og resultatet op med iPad'ens danske stemme (Indstillinger → Tilgængelighed → Oplæst indhold → Stemmer → Dansk: hent gerne den "forbedrede" stemme, så lyder den bedre). Slå fra under *Mere → Stemme*.
- **Tegninger:** hver øvelse har en lille animeret figur, der viser bevægelsen. Virker offline.
- **Egne videoer (anbefalet!):** film 10–15 sekunder af far/mor eller barnet selv, der laver øvelsen, og læg filen i mappen `media/` i repoet med øvelsens id som navn, fx `media/crossover.mp4` (id'erne står i `DRILLS`-listen i `index.html`, fx `layup_h`, `mellem_ben`). Så vises videoen i stedet for tegningen. Eksportér fra iPhone som "Mest kompatibel" (H.264) og hold filerne små (under ~10 MB), så de også kan caches offline. GitHub Pages har en grænse på 1 GB for hele repoet.

## Tilføj eller ret øvelser

Øvelserne ligger i `index.html` i listen `DRILLS` (søg efter `ØVELSESBIBLIOTEK`). Hver øvelse har `level` (1–4), `steps` med mål pr. trin
(fx `{label:'Højre hånd', n:50}`), `score:true` hvis tælleren er scoringer, og `lookUp:true` for påmindelsen "Kig op". Testene ligger i `BENCHMARKS`.
