# Mantorps migration report

## Sammanfattning

Webflow-exporten har migrerats till en svensk statisk webbplats for Mantorps Smadjursklinik. Layout, Webflow-klasser, animationer och komponentstruktur har behallits; arbetet har varit inriktat pa innehall, metadata, lankar, bilder och SEO.

## Andrade filer

- `index.html`
- `css/mantorps.webflow.shared.ecda39306.min.css` (omdopt fran tidigare template-namn)
- `images/mantorps/*`
- `MANTORPS_MIGRATION_REPORT.md`

Rensat bort:

- gamla stockbilder med lakar-, besoks-, apoteks- och vardtema
- tidigare varumarkesnamngiven CSS-fil
- gammalt granskningsscript fran template-exporten

## Uppdaterade sidor och sektioner

- Startsida: hero, CTA, telefon, drop-in vaccination, huvudbudskap och prioriterade tjanster
- Om oss: Linda & Linda med personal, teamkort och varm svensk klinikcopy
- Tjanster: tandvard, vaccination, poliklinik, ultraljud, rehabilitering, kirurgi/akutsjukvard, pass/chip/rabies och HD/ED-rontgen
- Prislista: kategoriserad prisinformation med betalning, direktreglering och avbokningsvillkor
- Kontakt: telefon, e-post, adress, oppettider, drop-in-information och Facebook-lank
- Footer: svensk navigering, kontaktuppgifter och klinikens budskap
- SEO: svensk title/description, lokala sokord och JSON-LD for VeterinaryCare

## Kallor

Innehall har hamtats och sammanfattats fran:

- https://mantorps-smadjursklinik.webnode.se/
- https://mantorps-smadjursklinik.webnode.se/om-oss/
- https://mantorps-smadjursklinik.webnode.se/prislista/
- https://mantorps-smadjursklinik.webnode.se/kontakt/

Facebook-lanken har lagts in, men Facebook anvandes inte som faktakalla eftersom sidan inte gick att lasa publikt i arbetsmiljon.

## Bilder

Bytta bilder:

- logotyp och djurbilder fran Mantorps Smadjurskliniks nuvarande Webnode-sida har lagts i `images/mantorps/`
- generiska stockbilder har tagits bort fran HTML och arbetskatalog
- gamla favicon-lankar pekar nu pa Mantorps-loggan

Bilder som bor godkannas av kund fore publicering:

- samtliga importerade Webnode-bilder i `images/mantorps/`
- eventuell exakt koppling mellan personalnamn och bildmaterial, om kunden vill anvanda personportratt
- inga Facebook-bilder anvandes

## Borttagen template-copy

Foljande typer av template-innehall har tagits bort eller ersatts:

- tidigare template-varumarke och engelsk Webflow-copy
- engelsk copy om humanvard, apotek, tidsbokning och generiska vardbesok
- fiktiva testimonials/recensionsliknande texter
- generiska CTA-texter och template-lankar
- Webflow granskningsscript

## Manuell kontroll fore publicering

- Bekrafta att alla priser fran prislistan fortfarande ar aktuella.
- Bekrafta oppettider och drop-in-regler, framfor allt information om kaninvaccination och rabiesvaccination.
- Godkann bildurvalet och eventuell person-/teamkoppling.
- Kontrollera om kliniken vill ha fler egna interiorbilder i stallet for djurbilder fran befintlig webbplats.

## Layoutandringar

Inga avsiktliga layout-, spacing-, grid-, responsivitets- eller animationsandringar har gjorts. Enda tekniska designrelaterade andringen ar att CSS-filen doptes om till Mantorps och att borttagna template-bilder ersattes med Mantorps-bilder.
