# Mantorps live QA report

## Status

Live-QA blockerad av Vercel Deployment Protection.

Testad URL:

- https://mantorpsdjursklinik-7bys5be06-webbdesign.vercel.app

Resultat:

- Den angivna deploy-URL:en svarar med `302` och skickar vidare till `https://vercel.com/login?...`.
- Slutlig renderad sida i Playwright är Vercels inloggningssida med title `Login – Vercel`.
- Vercels åtkomstverktyg kunde inte skapa en temporär share-länk för deployen.

## Screenshots

Sparade full-page screenshots:

- `qa-screenshots/desktop-1440.png`
- `qa-screenshots/tablet-768.png`
- `qa-screenshots/mobile-390.png`

Alla tre screenshots visar Vercel-login, inte Mantorps Smadjursklinik.

## Godkant

- Playwright kunde nå den angivna hosten tekniskt.
- Ingen horisontell scroll observerades pa Vercels loginvy i desktop, tablet eller mobil.
- Screenshots har sparats i begard mapp.

## Ej godkant / blockerare

- Sidan laddar inte Mantorps Smadjursklinik publikt.
- Forsta skarmen sager inte Mantorps Smadjursklinik.
- Innehall, CTA:er, footer, bilder och SEO for Mantorps-sidan kan inte verifieras pa live-URL:en eftersom deployen ar skyddad bakom Vercel-login.

## Vad som fortfarande ar template

Inget template-innehall kunde verifieras pa live-deployen, eftersom sidan inte renderas. Playwright ser bara Vercels loginvy.

## Exakta texter som maste bytas

Inga Mantorps-texter kunde inspekteras pa live-deployen.

Texter som syns pa den blockerade live-URL:en:

- `Log in to Vercel`
- `Continue with Email`
- `Continue with Google`
- `Continue with GitHub`
- `Continue with Apple`
- `Continue with SAML SSO`
- `Continue with Passkey`
- `Don't have an account? Sign Up`

Detta ska inte bytas i projektets HTML; det ska atgardas genom att gora deployen publikt atkomlig eller dela en fungerande Vercel share-lank.

## Sektioner som behover fixas

P0:

- Vercel Deployment Protection / access for preview deployment.

Ej verifierbara pa live forran P0 ar lost:

- Hero / forsta skarmen
- Tjanster
- Om oss
- Prislista
- Kontakt
- Footer
- SEO metadata
- Bildval och bildkansla
- CTA-lankar

## Mobilproblem

- Inga Mantorps-specifika mobilproblem kunde verifieras pa live.
- Den blockerade Vercel-loginvyn hade ingen horisontell scroll vid 390px.

## Bildproblem

- Inga Mantorps-bilder kunde verifieras pa live.
- Vercel-loginvyn visar inga klinikbilder.

## Lankproblem

Kritiskt:

- Den angivna URL:en skickar vidare till Vercel-login i stallet for den statiska sidan.

Ej verifierbart:

- `tel:0142661980`
- `mailto:kund@mantorpssmadjursklinik.se`
- interna CTA-lankar
- Facebook-lank

## SEO-problem

Kritiskt pa live-URL:en:

- Renderad title ar `Login – Vercel`, inte `Mantorps Smadjursklinik | Personlig djursjukvard i Mantorp`.
- Meta description for Mantorps-sidan kunde inte lasas eftersom Vercel-login renderas.

## Sarskild termsokning

Sokta termer:

- Loguna
- Modern Healthcare
- Doctor
- Patient
- Patients
- Healthcare
- Pharmacy
- Family Medicine
- Appointment
- Dr. Amanda Wilson
- California
- happy clients
- Trusted by 250+

Resultat:

- Inga av termerna hittades i den renderade Vercel-loginvyn.
- Den faktiska Mantorps-sidan kunde inte kontrolleras pa live-URL:en.

## Prioriterad fixlista

1. Gor deployen publikt atkomlig, eller skapa en fungerande Vercel share-lank med auth-bypass.
2. Rerun live-QA mot den publika eller share-baserade URL:en.
3. Verifiera forsta skarmen, svensk copy, kontaktuppgifter, CTA:er, footer, SEO och bildkansla pa live.
4. Om live fortfarande visar gammalt innehall efter access-fix: redeploya senaste `main`.

## Kommandon / metod

- Browser runtime forsokte oppna URL:en och hamnade pa `Login – Vercel`.
- Vercel access-tool forsokte skapa share-lank men returnerade `success: false`.
- Playwright med system-Chrome sparade screenshots i 1440px, 768px och 390px.
- Playwright noterade `302` fran deploy-URL:en till Vercel-login och slutstatus `200` for login-sidan.
