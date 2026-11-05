# Udgiv Basketbold på GitHub (så den kan åbnes på iPad'en)

Vælg én af de to måder. Begge tager under 5 minutter. Du skal bruge en GitHub-konto (gratis).

## Måde A – uden git, direkte i browseren (nemmest)

1. Gå til https://github.com/new
   - Repository name: `basketbold`
   - Vælg **Public** (GitHub Pages er gratis for public repos)
   - Sæt flueben i **Add a README file** (så repoet ikke er tomt) → **Create repository**
2. I det nye repo: klik **Add file → Upload files**.
   Træk ALLE filer fra denne mappe ind (også `sw.js`, `manifest.webmanifest`, ikonerne og `.nojekyll` – vis skjulte filer med ⌘⇧. i Finder).
   Klik **Commit changes**.
3. Klik **Settings** (øverst i repoet) → **Pages** (i venstre menu).
   Under *Build and deployment*: Source = **Deploy from a branch**, Branch = **main**, mappe = **/ (root)** → **Save**.
4. Vent ca. 1 minut og genindlæs Pages-siden. Der står nu:
   `Your site is live at https://<brugernavn>.github.io/basketbold/`

## Måde B – med git fra terminalen

Denne mappe er allerede et git-repo med ét commit. Opret repoet på https://github.com/new (uden README), og kør så:

```bash
cd basketbold
git remote add origin https://github.com/<brugernavn>/basketbold.git
git push -u origin main
```

Slå derefter Pages til som i trin 3–4 ovenfor. (Har du `gh` installeret: `gh repo create basketbold --public --source=. --push` gør det hele.)

## På iPad'en

1. Åbn `https://<brugernavn>.github.io/basketbold/` i **Safari**.
2. Tryk på del-ikonet (firkant med pil op) → **Føj til hjemmeskærm** → **Tilføj**.
3. Åbn appen fra hjemmeskærmen. Første gang: skriv navn. Gå derefter i **Mere → Forældre-menu** og sæt evt. PIN.
   Appen virker herefter også uden internet.

## Når du retter noget senere

1. Ret `index.html` (eller læg videoer i `media/`).
2. Åbn `sw.js` og skift `basketbold-v4` til `basketbold-v5` (osv.) – ellers beholder iPad'en den gamle version.
3. Upload/commit igen. Næste gang appen åbnes med net, henter den den nye version (luk og åbn appen én gang ekstra, hvis den ikke er skiftet).
