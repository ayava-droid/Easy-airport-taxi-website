# Easy Airport Taxi — website

Een statische onepager. Geen build-stap, geen framework, geen server.
Je opent `index.html` in een teksteditor, past aan wat je wilt, en zet het terug online.

---

## Wat er al ingevuld staat

Zoek in `index.html` naar deze plekken en vervang ze:

Niets meer. Je KvK-nummer (69310041), je domein (easyairporttaxi.nl) en je
telefoonnummer staan er al goed in, in beide talen.
Als dat ooit verandert, zoek dan op `31624242791` — het staat op zeven plekken,
vervang ze allemaal.

---

## Online zetten via GitHub Pages

### 1. Repository aanmaken

1. Maak een account op github.com als je die nog niet hebt.
2. Klik rechtsboven op **+** → **New repository**.
3. Naam: `easy-airport-taxi`. Zet hem op **Public**.
4. Klik **Create repository**.

### 2. Bestanden uploaden

Op de lege repository-pagina klik je op **uploading an existing file**.
Sleep de volledige inhoud van deze map erin:

```
index.html
en/
README.md
robots.txt
sitemap.xml
assets/
fonts/
```

Let op: sleep de *inhoud*, niet de map `site` zelf. `index.html` moet
in de hoofdmap van de repository staan, niet in een submap.

Klik onderaan op **Commit changes**.

### 3. Pages aanzetten

1. Ga in de repository naar **Settings** → **Pages**.
2. Bij *Source* kies je **Deploy from a branch**.
3. Branch: `main`, map: `/ (root)`. Klik **Save**.

Na een minuut staat je site op `https://JOUWNAAM.github.io/easy-airport-taxi/`.
Test hem daar eerst voordat je het domein koppelt.

### 4. Eigen domein koppelen

**Bij je domeinregistrar** (TransIP, Versio, Antagonist, Namecheap) zet je
deze DNS-records klaar:

Vier A-records voor het domein zelf (`easyairporttaxi.nl`):

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

En één CNAME-record voor `www`, zodat mensen die `www.` intikken ook
op je site komen:

```
Naam:   www
Waarde: JOUWNAAM.github.io
```

GitHub stuurt bezoekers van `www.easyairporttaxi.nl` dan automatisch
door naar `easyairporttaxi.nl`.

**Terug op GitHub**, bij **Settings** → **Pages** → *Custom domain*,
vul je `easyairporttaxi.nl` in en klik je **Save**. GitHub maakt dan
automatisch een `CNAME`-bestand aan in je repository.

Wacht tot de melding *DNS check successful* verschijnt — dat kan tot
24 uur duren, meestal is het binnen een uur. Vink daarna
**Enforce HTTPS** aan.

---

## Twee talen

De site bestaat uit twee pagina's:

- `index.html` — de Nederlandse versie, op `easyairporttaxi.nl`
- `en/index.html` — de Engelse versie, op `easyairporttaxi.nl/en/`

Rechtsboven staat een knop om te wisselen. In de code staat bij allebei een
`hreflang`-verwijzing naar de ander, zodat Google weet dat het dezelfde pagina
in een andere taal is. Een Engelstalige zoeker krijgt dan vanzelf de Engelse
versie te zien.

**Belangrijk:** als je iets aanpast — je telefoonnummer, een tekst, je
KvK-nummer — moet je dat in allebei de bestanden doen. Ze zijn los van elkaar.

Het aanvraagformulier op de Engelse pagina stuurt je een bericht in het
Engels, met de datum voluit geschreven (`21 September 2026`) zodat er geen
misverstand kan ontstaan over dag en maand.

## Iets aanpassen

Ga in GitHub naar `index.html` (of `en/index.html`), klik op het potloodje rechtsboven, pas de
tekst aan en klik op **Commit changes**. Binnen een minuut staat het online.

De teksten staan onderin het bestand, na de regel `<body>`. Alles daarboven
is opmaak — daar hoef je niet aan te zitten.

---

## Hoe het aanvraagformulier werkt

Er is geen server en geen database. Als iemand het formulier invult en op
de knop drukt, bouwt de site daar een WhatsApp-bericht van en opent die
in WhatsApp — bij de bezoeker op zijn eigen telefoon of in WhatsApp Web.
De bezoeker drukt zelf op verzenden, en het bericht komt bij jou binnen
alsof hij het zelf getypt heeft.

Voordelen: geen kosten, geen onderhoud, geen privacyverplichtingen, en je
kunt meteen terugappen in hetzelfde gesprek.

Eén ding om te weten: de bezoeker moet zelf nog op verzenden tikken.
Een enkeling haakt daar af. Daarom staat je telefoonnummer er overal bij.

---

## Bestanden

| Bestand | Wat het is |
| --- | --- |
| `index.html` | De Nederlandse pagina: tekst, opmaak en formulier |
| `en/index.html` | De Engelse pagina, met dezelfde opbouw |
| `assets/` | Favicon en de deelafbeelding voor WhatsApp |
| `fonts/` | De lettertypen, lokaal opgeslagen |
| `robots.txt`, `sitemap.xml` | Vertellen Google dat de site geïndexeerd mag worden |

De logo's staan rechtstreeks in `index.html`, niet als los bestand. Daardoor
zijn ze altijd zichtbaar, ook als je het bestand los opent zonder de rest
van de map erbij.

De lettertypen staan bewust in je eigen repository en worden niet bij
Google opgehaald. Dat is sneller en scheelt je een cookiemelding.
