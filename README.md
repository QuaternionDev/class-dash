# Osztálytermi Eszköztár

Egy középiskolai osztály számára épített, egymással összehangolt webalkalmazás-csomag. A projektek mind ugyanazt a technológiai alapot és vizuális stílust követik: vanilla HTML/CSS/JS, és egyetlen `index.html` fájl telepítés

A projekt megtekintéséhez látogassanak el a https://digiproject.quaternion.hu oldalra. 

---

## Projektek

A forráskódok az alábbi hivatkozásokra kattintva megtekinthetők. A versenyre általunk beadott kód minden repository special branch-én található, hiszen később szeretnénk folytatni a projekt fejlesztését, és ezért jobbnak láttuk elkülöníteni a kódvariációkat.

| Repo | Leírás |
|---|---|
| [`oral-draw`](https://github.com/QuaternionDev/oral-draw/tree/special) | Szóbeli felelős-sorsoló |
| [`home-works`](https://github.com/QuaternionDev/home-works/tree/special) | Házifeladat-kezelő |
| [`class-chat`](https://github.com/QuaternionDev/class-chat/tree/special) | Valós idejű osztálycsevegő |
| `class-dash` (ez a repo)| Közös belépési felület |

---

## Közös elvek

Az összes alkalmazás ugyanazt az architektúrát és dizájnrendszert követi:

- **Egyetlen fájl:** A teljes frontend egyetlen `index.html`, ami bármilyen statikus tárhelyen futtatható (Netlify, GitHub Pages, Vercel stb.)
- **Előnézet mód:** Minden alkalmazás fiók nélkül is kipróbálható, mintaadatokkal feltöltve
- **Többnyelvűség:** Magyar, angol és német felület, localStorage-ban tárolt beállítással
- **Reszponzív UI:** Mobil-barát, alsó navigációs sávval
- **Admin kezelőfelület:** Az admin kezelőfelületen keresztül a rendszer fentartói könnyen felügyelhetik a rendszert

---

## oral-draw

**Web-alapú szóbeli felelő-sorsoló osztálytermi használatra.**

A történelem órákon minden alkalommal valakinek szóbeli feleletet kell tartania. Ahelyett, hogy a tanár meglepetésszerűen szólítana fel valakit, a diákok önként jelentkezhetnek,
és az óra kezdete előtt a rendszer automatikusan kisorsolja egyiküket.

### Működés

1. Az admin létrehoz egy sessiont (dátum, tantárgy, határidő)
2. A diákok bejelentkeznek és jelentkeznek az általuk vállalt alkalomra
3. A határidő lejártakor a rendszer véletlenszerűen húz egyet a jelentkezők közül, és a sessiont `picked` állapotba teszi
4. Ha senki sem jelentkezett, a session `failed` lesz - a tanár az órán dönt
5. Az utoljára húzott diák a következő sessionből ki van zárva

### Funkciók

- Session lista - `open`, `picked`, `failed`, `locked` állapotokkal
- Felelésre jelentkezés és visszavonás a határidő előtt
- Automatikus sorsolás a határidő lejártakor
- Osztálytársak nézet - ki hányszor adott elő és mikor
- Admin panel - session létrehozás, szerkesztés, törlés; adatok törlése
- Előnézet mód - fiók nélkül is teljes UI

---

## home-works

**Házifeladat-kezelő webalkalmazás osztálytermi használatra.**

A diákok házifeladat-ticketeket adnak be (tantárgy, határidő, leírás), az admin jóváhagyja vagy elutasítja azokat, a jóváhagyott feladatok pedig beadási határidő szerint rendezve jelennek meg.

### Működés

1. A diák bejelentkezik és bead egy házifeladat ticketet (tantárgy, határidő, leírás)
2. A ticket az admin panelen `pending` állapotban várakozik
3. Az admin jóváhagyja vagy elutasítja
4. A jóváhagyott ticketek megjelennek az osztály közös feedjén
5. A diákok a saját ticketeiket státusz szerint szűrhetik és törölhetik

### Funkciók

- Ticketrendszer `pending`, `approved`, `rejected` állapotokkal
- Közös feed - jóváhagyott házifeladatok határidő szerint rendezve
- Admin panel - ticketek jóváhagyása, elutasítása, törlése
- Előnézet mód - mintaadatokkal, fiók nélkül

---

## class-chat

**Valós idejű osztálycsevegő Discord-stílusú csatornaszervezéssel.**

A diákok tantárgy-csatornákon üzenhetnek egymásnak valós időben. A csatornák csoportokba vannak rendezve (pl. Global, 1. csoport, 2. csoport), 
az üzenetek markdown-formázást, fájlmellékleteket és emoji-reakciókat is támogatnak.

### Működés

1. A diák bejelentkezik a class accountjával
2. Az oldalsávon csoportok láthatók - rákattintva előjönnek az alcsatornák
3. Egy csatornára kattintva betöltődik az chat history
4. Az üzenetek markdown-formázással jelennek meg, képekhez lightbox nyílik
5. Az admin létrehozhat/törölhet csatornákat, és bármelyik üzenetet törölheti

### Funkciók

- Könnyű navigáció
- Markdown támogatás - félkövér, dőlt, áthúzott, kód blokk, idézet, lista
- Fájlmellékletek - képek (lightboxszal), videók, dokumentumok (max. 50 MB)
- Emoji reakciók - hat gyorsreakció üzenetenként
- Admin panel - csatorna létrehozás/törlés, üzenet törlés
- Előnézet mód - mintaüzenetekkel, fiók nélkül

---

## class-dash

**Közös belépési felület az összes osztálytermi eszközhöz.**

A dashboard egy egységes hub, ahol a diákok egy helyről érik el az összes alkalmazást. Körbeölelő stílussal és könnyű belépéssel fogadja a felhasználókat.

### Funkciók

- Egységes belépési pont a weboldal minden funkciójához
- Egy helyen látható az aktív sorsolás állapota, közelgő házifeladatok és új üzenetek
- Konzisztens vizuális stílus

---
Csapatunk:
Bence0327 - Molnár Bence
SPARFahejasCsiga - Ivanovics Emma
QuaternionDev - Südi Balázs
m1lkacsokker - Kis Milán

---

> A fejlesztés a Claude (Anthropic) segítségével zajlott, interatktív, párbeszédalapú folyamatban.

---
Lincenc

MIT
