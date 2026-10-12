# AGENTS.md – Grøn Start

## 1. Projektbeskrivelse

- Arbejd som en professionel frontendudvikler.
- Byg Grøn Starts forside som én responsiv `index.html` til desktop og mobil.
- Forsiden består kun af header, hero, en “How to”-sektion med tre trin og footer.
- Bevar den præcise danske tekst og det varme, minimalistiske udtryk fra Figma.
- Designanalysen beskriver også undersider. Byg ikke disse eller deres plantekort i denne opgave.

## 2. Teknologier

- Brug kun HTML og CSS.
- Brug CSS Grid, Flexbox og media queries til responsive layouts.
- Brug ingen JavaScript, inline-eventhandlers, frameworks eller JavaScript-biblioteker.
- Løsningen er statisk uden backend, database, login, profiler, betalinger eller API-integration.

## 3. Projektstruktur

- Placér `index.html` i projektets rod.
- Placér CSS, billeder og fonte under `assets/`.
- Brug en separat stylesheet, fx `assets/css/styles.css`.
- Placér tilgængelige fontfiler under `assets/fonts/`.
- Følg projektets eksisterende struktur inden for disse krav.
- Bevar denne AGENTS.md og designanalysen som projektinstruktioner.

## 4. Arbejdsform

- Undersøg eksisterende kode, projektinstruktioner og ændringer før redigering.
- Lav så få ændringer som nødvendigt, og bevar uvedkommende filer og arbejde.
- En eksisterende `index.html` eller stylesheet må kun ændres, hvis den tilhører Grøn Start.
- Spørg før overskrivning, hvis et nødvendigt filnavn tilhører en anden løsning.
- Tilføj ikke nye frameworks eller biblioteker uden tilladelse; den aktuelle løsning skal fortsat være HTML og CSS.
- Undersøg Figma og projektfiler først. Gæt ikke, hvis vigtig information stadig mangler.

### Designkilder og prioritet

- Codex har adgang til Figma via MCP. Hent designkontekst og screenshots af begge forsideframes før implementering.
- Figma: https://www.figma.com/design/6LYDS1rycpMHjMLenHkeGk/Temaopgave-2---Uzma?node-id=3-95
- Filnøgle: `6LYDS1rycpMHjMLenHkeGk`.
- Desktop: `9:352` – “Forside - Desktop”.
- Mobil: `39:952` – “Forside - Mobil”.
- Læs `design-analyse-v2(2).md`. Find den tilsvarende analyse, hvis filen er omdøbt.
- Ved modstrid gælder: eksplicitte krav og rettelser her → konkrete Figma-frames → Markdown-designanalyse.
- Footerfarve og knappernes hoverfarver her har forrang over Figma.

## 5. Andre vigtige ting ift. projektet

### Komponenter og responsivt layout

| Komponent | Desktop | Mobil |
|---|---|---|
| Header | Logo til venstre, vandret navigation til højre | Logo til venstre; ingen navigation eller hamburgermenu |
| Hero | H1, tekst og primær CTA til venstre; planten synlig til højre | H1, tekst og CTA under hinanden, derefter billedet |
| How to | H2 over tre nummererede trin i én række med lodrette skillelinjer | H2 over tre stablede trin med vandrette skillelinjer |
| Footer | Logo og SoMe til venstre; navigation til højre | Følg Figmas lodrette opstilling; alle fire navigationslinks skal være synlige |

- Hvert trin indeholder H3 og brødtekst.
- Undersøg heroens billedlag: gengiv den faktiske komposition, herunder billedets placering bag teksten på desktop.
- Match billedbeskæring, position, eventuelle afrundede hjørner, ikoner og skillelinjer til Figma.
- Mobilfooterens logo følger Figma, hvis det er vist.

### Farver

Definér fælles CSS-variabler:

| Farve | Hex | Anvendelse |
|---|---|---|
| Dark Brown | `#302B25` | Overskrifter, tekst, headerlogo, headernavigation og footerbaggrund |
| Hot Creme | `#FAF7F2` | Sidebaggrund og tekst på primær CTA |
| Dusty Green | `#435443` | Primær CTA-baggrund og sekundær CTA-tekst |
| Light Beige | `#EDE5D9` | Sekundær CTA-baggrund samt footerlogo, SoMe og links |

### Typografi

| Element | Font og vægt | Desktop | Mobil |
|---|---|---|---|
| Logo | Fraunces SemiBold | Hent størrelse fra Figma | Hent størrelse fra Figma |
| Display, hvis brugt | Fraunces Regular | 48 px | Hent fra Figma |
| H1 | Jost Medium | 48 px | 34 px |
| H2 | Jost Medium | 30 px | 26 px |
| H3 | Jost Medium | 22 px | 20 px |
| Brødtekst | Jost Regular | 18 px / 28 px linjehøjde | 18 px / 28 px linjehøjde |
| Knapper | Jost Medium | Hent fra konkret CTA-lag | Hent fra konkret CTA-lag |

- Hvis Figma angiver 16 px knaptekst og analysen 18 px, brug Figma-værdien og oplys den i afslutningen.
- Hent øvrige linjehøjder og navigationens tekststørrelser fra Figma.
- Brug de korrekte fonte; erstat dem ikke stiltiende med andre.

### Størrelser og afstande

| Mål | Desktopreference | Mobilreference |
|---|---|---|
| Framebredde | 1440 px | 390 px |
| Grid | 12 kolonner | 4 kolonner |
| Gutter | 24 px | 20 px |
| Sidemargin | 72 px | 24 px |
| Luft mellem hovedsektioner | Ca. 80 px | Ca. 40 px |

- Mobilens indholdsbredde er 342 px ved 390 px viewport.
- Desktopreferencen har headerhøjde 91 px, herohøjde ca. 499 px og CTA-højde 60 px.
- Undersøg Figma for placeringen af analysens interne afstande på 20 og 50 px.
- Brug fleksible bredder og indholdsstyrede højder. Frame-mål er referencer, ikke faste sidedimensioner.
- Layoutet skal fungere mellem referencestørrelserne uden overlap, beskæring af indhold eller vandret scrolling.

### Knaptilstande

| Knap | Normal | Hover |
|---|---|---|
| Primær CTA | Grøn `#435443` baggrund, creme `#FAF7F2` tekst | Beige `#EDE5D9` baggrund, grøn `#435443` tekst |
| Sekundær CTA, hvis vist | Beige `#EDE5D9` baggrund, grøn `#435443` tekst | Grøn `#435443` baggrund, creme `#FAF7F2` tekst |

- Implementér hover med CSS `:hover` og synligt tastaturfokus med `:focus-visible`.
- Match knapform, padding og mål til Figma.

### Navigation og SoMe

| Side | Destination |
|---|---|
| Forside | `index.html` |
| Begynderguide | `begynderguide.html` |
| Udstyr | `udstyr.html` |
| Din første plante | `din-foerste-plante.html` |

- Brug disse filnavne, også hvis destinationssiderne endnu ikke findes. Opret ikke undersiderne i denne opgave.
- Undersøg prototypeinteraktionerne i Figma for at vælge CTA-destination blandt de aftalte sider.
- Medtag alle fire destinationer i mobilfooteren.
- Brug kun SoMe-profiladresser, der findes i projektet eller kildematerialet.
- Hvis en adresse mangler, vis ikonet uden link eller klikfunktion, med en passende tilgængelig etiket og uden tastaturfokus.
- Brug ikke `href="#"` som pladsholder.

### Semantik, tilgængelighed og assets

- Brug semantiske `header`, `nav`, `main`, `section` og `footer`.
- Sæt `lang="da"`, og medtag viewport-meta-tag.
- Brug én H1 og en logisk overskriftshierarki.
- Bevar tekst og kontroller som rigtige HTML-elementer.
- Brug anchors til navigation og CTA'er, der fører til andre sider.
- Tilføj passende alt-tekster og tilgængelige navne til SoMe-links.
- Hent de faktiske Figma-assets efter MCP-instruktionerne, og referér til lokale filer.

## 6. Begrænsninger

- Byg kun den aftalte forside.
- Tilføj ikke nye sektioner, dekorative elementer eller funktioner.
- Brug ikke et screenshot af hele designet som hjemmeside.
- Erstat ikke fotografier eller ikoner med tilnærmelser.
- Efterlad ikke midlertidige Figma-asset-URL'er i den færdige kode.
- Opfind ikke SoMe-adresser, manglende oplysninger eller destinationssider.

## 7. Test og kvalitet

- Render og sammenlign siden med Figma ved 1440 px og 390 px bredde.
- Kontrollér også en mellemliggende bredde.
- Kontrollér billeder, beskæring, typografi, farver, afstande og justering.
- Kontrollér mørkebrun footer med beige indhold.
- Kontrollér desktopnavigation og alle fire navigationslinks i mobilfooteren.
- Kontrollér hover, tastaturfokus, CTA-destinationer og aftalte filnavne.
- Kontrollér, at SoMe-ikoner uden URL ikke er klikbare.
- Kontrollér, at indhold ikke overlapper, klippes eller giver vandret overflow.
- Kontrollér, at leverancen ikke indeholder JavaScript.

## 8. Svar fra CODEX

- Forklar kort, hvad der er bygget eller ændret.
- Oplys hvilke kontroller der er udført, og hvilke der eventuelt ikke kunne udføres.
- Oplys den anvendte fontstørrelse på knapper.
- Angiv manglende destinationssider og SoMe-profiladresser.
- Gør opmærksom på relevante fejl, risici, antagelser, manglende oplysninger og uløste kildekonflikter.
