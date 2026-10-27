# Første torsdag – nettside

Enkel, statisk arrangementsside for «Første torsdag». Svar og skriv på norsk (bokmål).

## Teknisk oppsett
- Én fil: `index.html` med all CSS og JavaScript inline. Ingen rammeverk, ingen byggesteg, ingen avhengigheter.
- Hostes på GitHub Pages fra `main` / rot. Domene: `førstetorsdag.no` (punycode: `xn--frstetorsdag-vjb.no`).
  DNS ligger hos Gigahost: fire A-rader på `@` til GitHubs IP-adresser (185.199.108–111.153) og CNAME `www` → `smoerbukk.github.io`.
- Filer i repoet ved siden av `index.html`: `overskrift.woff2`, `crow.png`, `crow2.png`, `crow3.png`, `glass.png`, `bottle.png`.
  Filnavn er små bokstaver, og GitHub Pages skiller mellom store og små.

## Design
- Mørk side (`#0e0d0a`) med gulhvit tekst (`#f4ecc4`). All tekst har samme farge.
- Tittelen er den eneste teksten med egen stil. All annen tekst har lik størrelse, vekt og skrift (ingen ulike vekter eller størrelser).
- Tittelfont: `Titteltype` (en subsettet woff2 av Sriracha Display, bare tegnene i «FØRSTE TORSDAG»), reserve Share Tech Mono.
  Brødtekst: Courier Prime (Google Fonts), skrivemaskinpreg.
- Hold designet enkelt og statisk. Ingen vin-animasjon.

## Lommelykt-effekten (den eneste effekten)
- Musepekeren (eller fingeren på mobil) fungerer som en lommelykt som viser en liten sirkel av siden i lys modus (kremhvit bakgrunn, mørk tekst).
- Implementert ved at JavaScript kloner `.content` inn i `.lit`-laget, som ligger oppå og vises gjennom en `radial-gradient`-maske som følger pekeren.
  Endrer du innholdet i `.content`, følger det lyse laget automatisk med.
- `RADIUS` i scriptet styrer størrelsen på lyset. Det respekterer `prefers-reduced-motion`.
- Illustrasjonene ligger bare i `.art` inni `.lit`, bak teksten, så de er kun synlige i lyset. Hver av de fem finnes to ganger, med
  varierende plassering. Plasseringen styres per `<img>` med `top` og `left` i prosent, `--s` (størrelse) og `--rot` (skråstilling).
  Det er greit at bildene overlapper teksten.

## Innhold (status)
- Ferdig: ingress, avsnitt om første torsdag i november, «Når» (torsdag 5. november kl. 19) og «Hvor» (gåten om dyret).
- Mer tekst kommer. Påmelding og kontaktlinje er foreløpig fjernet.

## Regler
- Fonten (Sriracha Display) har webfont-lisens, men skal ikke være lett å laste ned. Legg bare `overskrift.woff2` i repoet, aldri
  originalfilene (`.otf`/`.ttf`) eller lisensmappen. Skal tittelen endres, må woff2-filen lages på nytt med de nye bokstavene
  (`pyftsubset … --text="…" --flavor=woff2`).
- Bruk typografiske tegn i teksten (’ og tankestrek –), og behold norsk rettskriving.
- Redigér `index.html` direkte. Repoet er eneste kilde, så ingen kopier i chat.
