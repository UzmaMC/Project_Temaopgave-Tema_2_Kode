# Designanalyse – Grøn Start

Grundlag for implementering i Codex. Analysen er struktureret ud fra de oplyste tabeller. Uafklarede detaljer er markeret nederst; der er ikke tilføjet nye designbeslutninger.

## Frames og grid

| Egenskab | Desktop | Mobil |
| --- | --- | --- |
| Framebredde | 1440 px | 390 px |
| Kolonner | 12 | 4 |
| Gutter | 24 px | 20 px |
| Sidemargin | 72 px | 24 px |
| Luft mellem sektioner | Cirka 80 px | Cirka 40 px |

Auto Layout anvendes i navigation, cards og guidens trin. Den oplyste afstandsskala bruger 20 og 50 px; øvrige angivne afstande fremgår af afstandstabellen.

## Typografi

| Teksttype | Font | Vægt | Desktop | Mobil | Linjehøjde |
| --- | --- | --- | --- | --- | --- |
| Logo | Fraunces | SemiBold | Ikke angivet | Ikke angivet | Ikke angivet |
| Display | Fraunces | Regular | 48 px | Ikke angivet | Ikke angivet |
| H1 | Jost | Medium | 48 px | 34 px | Ikke angivet |
| H2 | Jost | Medium | 30 px | 26 px | Ikke angivet |
| H3 | Jost | Medium | 22 px | 20 px | Ikke angivet |
| Body | Jost | Regular | 18 px | 18 px | 28 px |
| Button | Jost | Medium | 18 px | 18 px | Ikke angivet |

Fortolkning af den indsatte typografitabel: SemiBold hører til logoet i Fraunces; 48 px Regular hører til Display i Fraunces. Denne kobling skal kontrolleres mod Figma.

## Styles og komponenter

- Styles: fælles farver og tekststørrelser.
- Komponenter: header, navigation, knap, plantekort og footer.
- Auto Layout: navigation, cards og guidens trin.
- På mobil står heroens tekst og billede under hinanden, og de tre trin stables lodret.

## Sektioner og responsivt layout

| Sektion | Indhold | Desktop | Mobil |
| --- | --- | --- | --- |
| Header | Logo og navigation | Logo til venstre. Vandret navigation til højre. | Logo til venstre. Ingen navigation i headeren, jf. komponenttabellen. |
| Forside: Hero | H1, tekst, billede og CTA-knap | Overskrift, tekst og knap til venstre. Billede til højre. | Elementerne står under hinanden. Billedet placeres under CTA-knappen. |
| Forside: How to | H2 og tre trin med H3 og tekst | H2 over tre trin på én række. H3 og tekst står under hinanden i hvert trin. | H2 over tre trin, som stables i tre rækker. |
| Begynderguide | Intro med H2 og tekst, How to, plantekort og CTA-knap | Intro øverst, derefter tre trin på én række. To plantekort i to kolonner nedenunder. CTA-knap nederst. | Intro, tre trin i tre rækker, plantekort under hinanden og CTA-knap nederst. |
| Udstyr | Intro med H2 og tekst, Equipment og CTA-knap | Intro øverst. I Equipment står billedet til venstre og udstyrslisten til højre. CTA-knap nederst. | Intro, billede, udstyrsliste og CTA-knap under hinanden. |
| Din første plante | Intro med H2 og tekst, Guide og CTA-knap | Intro øverst. Tre guiderækker, hver med billede til venstre og tilhørende trin til højre. CTA-knap nederst. | Intro øverst. Hvert billede står over sit tilhørende trin. CTA-knap nederst. |
| Footer | Logo, SoMe og navigationslinks | Logo og SoMe til venstre. Navigationslinks til højre. | Elementerne stables lodret. Logoets medtagelse og præcise rækkefølge skal bekræftes. |

## Komponentanalyse

| Komponent | Består af | Bruges hvor? | Variationer |
| --- | --- | --- | --- |
| Navigation | Tekstlinks | Header | Desktop: synlige tekstlinks. Mobil: ingen navigation i headeren. |
| Knap | Tekst og baggrund | Flere sektioner | Primær: grøn baggrund med cremefarvet tekst. Sekundær: beige baggrund med grøn tekst. |
| Plantekort | Billede, titel, tekst og knap | Cards-sektion | Samme struktur med forskelligt indhold. |
| Footer | Logo, SoMe og links | Forside og undersider | Desktop: logo og SoMe til venstre, navigationslinks til højre. Mobil: lodret opstilling. |

Header er nævnt som komponent, men har ikke en særskilt række i den oprindelige komponentanalyse. Layoutet fremgår af sektionstabellen.

## Knapper: normal og hover

| Knap | Normal baggrund | Normal tekst | Hover baggrund | Hover tekst |
| --- | --- | --- | --- | --- |
| Primær CTA | Grøn `#435443` | Creme `#FAF7F2` | Beige `#EDE5D9` | Grøn `#435443` |
| Sekundær CTA | Beige `#EDE5D9` | Grøn `#435443` | Grøn `#435443` | Creme `#FAF7F2` |

Alle primære grønne CTA-knapper får sekundærknappens farver ved hover. Den sekundære beige CTA-knap får primærknappens farver ved hover.

## Farver

| Farvenavn | Farvekode | Anvendelse |
| --- | --- | --- |
| Dark Brown | `#302B25` | Overskrifter, tekst, logo i header, navigationslinks i header og footerens baggrund. |
| Hot Creme | `#FAF7F2` | Sidens baggrund samt tekst på primær CTA-knap. |
| Dusty Green | `#435443` | Primær CTA-knaps baggrund samt tekst på sekundær CTA-knap. |
| Light Beige | `#EDE5D9` | Sekundær CTA-knaps baggrund samt logo, SoMe og links i footer. |

## Afstande

| Afstand | Cirka størrelse | Anvendelse |
| --- | --- | --- |
| Lille | 20 px | Mellem trin. |
| Mellem | 40 px | Undersider og mobil. |
| Stor | 80 px | Mellem sektioner på desktop. |

50 px er også angivet som en del af Auto Layout-afstandsskalaen, men anvendelsen er ikke specificeret.

## Punkter, der skal kontrolleres mod Figma

1. **Logo og Display:** Logoets størrelse mangler. Bekræft, at 48 px Regular gælder Display, og angiv eventuel mobilstørrelse.
2. **Afstande:** Bekræft, hvor 50 px bruges, og hvor afstanden 40 px på undersider gælder i forhold til 80 px mellem desktopsektioner.
3. **Mobilfooter:** Sektionstabellen nævner SoMe og links, mens komponenttabellen også nævner logo. Bekræft logo og elementernes rækkefølge.
4. **Mobilnavigation:** Headernavigation er angivet som fraværende på mobil. Footerens links skal derfor forbindes til siderne; der er ikke beskrevet en mobilmenu.
5. **Knaptilstande:** Normal- og hoverfarver er angivet i knaptabellen. Fokusudseende og overgang er endnu ikke angivet.
6. **Plantekort og CTA:** Tekster og destinationer for knapper og links skal aflæses i Figma eller specificeres separat.
7. **Figma-links:** Links til desktop- og mobilframes er endnu ikke angivet.

## Brug i Codex

Læs denne analyse sammen med Figma-designet før implementering. Bevar de oplyste værdier. Kontrollér markerede uklarheder mod Figma, og bed om afklaring, hvis designet ikke giver et tydeligt svar. Der skal ikke indføres ekstra komponenter eller funktioner på baggrund af antagelser.
