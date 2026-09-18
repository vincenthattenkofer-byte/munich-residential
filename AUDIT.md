# AUDIT.md · Bestandsaufnahme der Fassung vom 1. September 2026 (Commit d96c71f)

Geprüft in Chrome 152 headless bei 375, 768, 1440 und 1920 px, Screenshots im Ganzen und je
Abschnitt. Fundstellen beziehen sich auf `index.html` dieses Commits.

## A. Kaputt oder regelwidrig

1. **Google Fonts werden vom Server geladen** (Zeile 16 bis 18, `<link href="https://fonts.googleapis.com/…">`). Vier Fremdanfragen beim ersten Aufruf, in Deutschland ein Abmahnrisiko. Im Auftrag ausdrücklich verboten.
2. **Impressum und Datenschutz sind tote Links** (Zeile 703, `href="#"`). Eine Firmenseite ohne Impressum verstößt gegen § 5 DDG.
3. **Projekte haben keine eigene Adresse.** Der Hauptmangel der Altseite ist nicht behoben: Man kann kein Objekt verlinken, nur die Liste (`#arbeiten`).
4. **Drei KI-generierte Stimmungsbilder** (`assets/station-ankauf.jpg`, `-baurecht.jpg`, `-uebergabe.jpg`, Zeile 588 bis 601). Im Auftrag verboten. Sie zeigen außerdem keine Objekte der Firma und behaupten damit etwas, was kein Projekt belegt.
5. **Alle 21 Projektbilder sind auf 1280 px hochgerechnet** (Lanczos plus Nachschärfen aus 616 px). Bei 1440 px Breite steht ein 616 px breites Originalbild auf 616 CSS-Pixeln, bei 1920 px auf 822 px. Auf Retina-Bildschirmen wird jedes Pixel vierfach gedehnt. Regel im Auftrag: höchstens das 1,3-Fache der nativen Breite.
6. **Zwei verschiedene Gebäude liefen unter „Hansastraße"** in der Altseite. Die zweite Ansicht wurde zwar nicht eingebaut, die Frage ist aber nirgends dokumentiert.
7. **Ein gefüllter Button in Akzentfarbe** (`.btn`, Zeile 165, `background:var(--accent)`), im Kopf und im Formular. Der Auftrag verbietet gefüllte Pill-Buttons; hier ist er eckig, aber gefüllt, und die Zoomleiste der Karte wiederholt das Muster (`.zbtn[aria-pressed="true"]`, Zeile 279).
8. **`!important` neunmal** (Zeile 425 bis 442), in den statischen Hero-Regeln und in reduced motion. Der Auftrag verlangt keines.
9. **Ein Icon im Bild** (`figure.hat-galerie::after`, Zeile 222 bis 227, ein Vollbild-Symbol als Daten-URL). Der Auftrag verbietet Icons.
10. **Das Plus-Zeichen in der FAQ** (`.faq summary::after{content:"+"}`, Zeile 385) ist ein Icon im Sinne des Auftrags, nur als Text getarnt.
11. **Die Karte nutzt Satellitenkacheln** (`assets/karte-*.jpg`, 1,3 MB in fünf Dateien). Zulässig war eine selbst gezeichnete, abstrahierte Karte. Das Foto-Basisbild konkurriert außerdem mit den Projektfotos um Aufmerksamkeit.
12. **Der Datenschutz-Hinweis im Fuß nennt Sentinel-2 und OpenStreetMap** (Zeile 705, 545), also Quellen, die auf der Seite gar nicht mehr gebraucht werden, sobald die Karte selbst gezeichnet ist.
13. **Kein JSON-LD, keine kanonische Adresse** im `<head>` (Zeile 1 bis 18). Suchmaschinen sehen eine Seite ohne Organisation, Anschrift oder Telefonnummer.
14. **Kein Skip-Link-Ziel mit Fokusführung nach Hash-Navigation**: `#main` hat `tabindex="-1"` (gut), aber die Abschnittsanker (`#arbeiten` etc.) bekommen nach dem Sprung keinen Fokus. Tastaturnutzer landen mit dem Fokus noch in der Navigation.
15. **Doppelte Regel** `.plan svg{width:100%;height:100%}` direkt gefolgt von `.plan svg{width:100%;height:auto;…}` (Zeile 283 f.). Totes CSS.
16. **Der Lageplan hat ein Scroll-Verhalten `scroll-behavior:smooth` auf `html`** (Zeile 39), das die Sprünge aus der Karte ins Archiv weich macht, aber auch jeden Ankersprung, auch für Nutzer mit reduzierter Bewegung (dort zwar ausgeschaltet, aber nur über `!important`).

## B. Generisch, nach Vorlage oder nach KI

17. **Alle sieben Abschnitte beginnen gleich**: Mono-Kicker in Versalien, darunter eine Lede, darunter Inhalt (Zeile 460, 491, 511, 583, 623, 637, 665). Der Auftrag verlangt ein eigenes Skelett pro Abschnitt; die Seite hat eines für alle.
18. **Die Sektionsabstände sind überall identisch** (`section{padding:clamp(90px,13vh,170px)…}`, Zeile 178). Kein Rhythmus, keine Verdichtung, keine Pause.
19. **Zwei Zweispalter direkt hintereinander** (Ankaufsprofil, Zeile 623, und Kontakt, Zeile 665) mit demselben Raster `1fr 1fr` und derselben Lede-links-Liste-rechts-Logik wie „Das Haus" (Zeile 460).
20. **Der Hover-Zoom auf Bildern** (`.work:hover img{transform:scale(1.04)}`, Zeile 213) ist das häufigste Template-Muster im Netz. Herzog & de Meuron würden das nicht machen.
21. **Ein Ladering** (`.ring`, Zeile 155, ein sich füllender Kreis rechts unten). Der Auftrag verbietet Spinner und Preloader.
22. **Der pulsierende Ring auf Kartenpunkten** (`.pin.live .ring{animation:puls…}`, Zeile 300 f.). Nichts darf pulsieren.
23. **Der Text im Archiv rückt beim Überfahren nach rechts** (`.work:hover .label{transform:translateX(10px)}`, Zeile 200). Eine Bewegung ohne Bedeutung.
24. **Der Satz „Was wir zusagen, halten wir. Das ist der ganze Anspruch, und die Liste unten ist der Beleg dafür."** (Zeile 467) ist Überredung. Der Auftrag will, dass das Werk spricht.
25. **„Der häufigste Grund, warum ein Grundstücksverkauf platzt, ist nicht der Preis. Es ist die Zeit dazwischen."** (Zeile 585) ist ein Werbetext-Kniff (Behauptung, Wendung, Pointe).
26. **Vier Beschreibungen, 17 Objekte ohne Text.** Zwei der vier (Zeile 730, 738) sind aus dem Bild geraten („Wohnanlage in Freising. Die Wohnungen wurden im Bestand saniert und neu übergeben."), belegt ist das nicht.
27. **Die Legende der Karte doppelt jeden Namen** („München und Umland | München und Umland 17", Screenshot 1440 px, Karte rechts). Ein Fehler in der Ausgabe von `eintraege.map` (Zeile 985 f.), bei dem Name und Beschriftungstext identisch sind.
28. **Der Kartentitel „Wo wir bauen"** (Zeile 512) ist ein Prospekt-Ton. Ein Werkverzeichnis sagt „Lageplan" oder „Orte".

## C. Layout und Typografie

29. **Das Archiv hat bei 1920 px eine leere Spalte von 480 px rechts** (`.work{grid-template-columns:.8fr 1.35fr .5fr}`, Zeile 190; Screenshot 1920 px). Die Leere ist gewollt, aber die Beschriftungsspalte ist mit 22 px Schrift zu klein für die Fläche links davon.
30. **Projektname und Ort sind bei 375 px kleiner als der Fließtext** (`.work h3{font-size:clamp(22px,…)}` gegen `body 16px`, aber die Mono-Zeile darunter 12 px auf 375 px sind mit 0,1 em Sperrung schwer lesbar, Screenshot 375 px Archiv).
31. **Die Fakten-Spalte im Haus steht auf Tabellenzeilen, die Lede daneben hat aber keine Grundlinie mit ihnen gemein** (Screenshot 1440 px, Haus: die Liste beginnt 20 px über der Lede).
32. **Der Kontakt-Fuß ist eine dreispaltige Flex-Zeile** (`footer{display:flex;justify-content:space-between}`, Zeile 407), in der die Offenlegung als 70-ch-Block rechts schwimmt und das Logo darüber allein steht. Kein Raster, nur Verteilung.
33. **Die Formularfelder sind Kästen mit Rahmen und Fläche** (`.field input{background:var(--panel);border:1px solid…}`, Zeile 391). Der Auftrag verlangt Unterstrich-Felder ohne Kästen.
34. **Die Filterleiste** (Zeile 486) filtert nur nach Status. Nach Ort lässt sich nicht filtern; die Zeilen verschwinden per `display:none` (Zeile 194), nichts wird animiert.
35. **Keine Listen- oder Rasteransicht, keine Tastaturführung im Archiv, keine Zeiger-Vorschau.** Alles drei im Auftrag.
36. **Die Bänder im Kopf haben eine Textschattierung mit drei Ebenen** (`--tshadow`, Zeile 32), die bei 76 px Schrift einen sichtbaren Halo erzeugt (Screenshot 1440 px Kopf, „Wir entwickeln in München"). Ein Schlagschatten, im Auftrag verboten.
37. **Die Mobilnavigation ist eine Einzeile mit vier 10 px-Links** (`@media (max-width:640px) .nav{font-size:10px}`, Zeile 64). Touch-Ziele unter 44 px. Der Auftrag verlangt ein Vollflächen-Menü mit dem Wort „Menü".
38. **Die Schrift-Ersatzfamilie ist nicht angepasst** (`--display:'Archivo',system-ui`, Zeile 28). Ohne `size-adjust` springt der Umbruch beim Schriftwechsel, das treibt CLS.

## D. Barrierefreiheit und Kontraste, nachgerechnet

| Paar | Wert | Ergebnis |
|---|---|---|
| `--ink` #15181B auf `--canvas` #F2F1ED | 16,2 : 1 | gut |
| `--text-secondary` #6A6E72 auf `--canvas` | 4,55 : 1 | knapp, AA für Fließtext |
| `--accent` #2A5B65 auf `--canvas` | 6,54 : 1 | gut |
| Mono 12 px `#6A6E72` in Versalien mit 0,16 em Sperrung (Kicker) | 4,55 : 1 | erfüllt AA rechnerisch, wirkt aber bei 12 px zu leicht |
| Nav-Links weiß mit `opacity:.78` über dem Film | 4,9 bis 5,3 : 1 | erfüllt, nur wegen des Scrims |
| Zoomleiste `#6A6E72` auf `--canvas` mit 1 px Rahmen | 4,55 : 1 | erfüllt |

39. **Kartenpunkte sind `<g tabindex="0" role="button">`** (Zeile 940). Das funktioniert, aber SVG-Gruppen mit `role=button` werden von Screenreadern uneinheitlich vorgelesen. Besser echte `<button>` in der Legende, die Karte nur als Spiegel.
40. **Die Galerie fängt den Fokus mit eigenem Tab-Handler** (Zeile 795 bis 801), aber `aria-modal` sitzt auf einem `div` ohne `aria-labelledby`, und der Hintergrund bekommt kein `inert`.
41. **`<video aria-hidden="true">` ohne Beschreibung des Films.** Der Film trägt den Kopf, ein Screenreader erfährt nichts. Ein `<figcaption>` oder ein `sr`-Text fehlt.

## E. Leistung

42. **5,5 MB Film werden auf jedem Desktop geladen**, auch wenn der Besucher nie scrollt. Akzeptabel per Auftrag (Scroll-Video), aber `priority:'low'` allein reicht nicht; der Film sollte erst nach dem ersten Bild beginnen (macht er, Zeile 1206), das ist in Ordnung.
43. **Satellitenkacheln 1,3 MB** plus Stationen 0,3 MB plus 21 Projektbilder à 200 KB = etwa 6 MB Bilder für eine Seite mit 616 px-Quellen. Die nativen Originale wiegen zusammen 1,4 MB.
44. **Kein `<link rel="preload">` für die Schrift, kein `size-adjust`**, also sichtbares Nachrücken beim Laden.

## F. Was bleibt, weil es gut ist

- Der Scroll-Film mit der Bandtabelle aus `design-package.md`, samt Flick-Test, Lesbarkeitsprüfung und den fünf statischen Toren. Wird übernommen, entschlackt (kein Ring, kein Schatten).
- Die Halten-Interaktion. Signatur der Seite, bleibt, wird auf die handgezeichnete Linie verlegt.
- Die Farbwerte, die Schriften, das mailto-Formular mit ehrlicher Erfolgsmeldung.
- Die echten Koordinaten aus der Adresssuche (21 Objekte), sie treiben jetzt die gezeichnete Karte.

## G. Kontraste der neuen Fassung, nachgerechnet (WCAG 2.2, relative Leuchtdichte)

| Paar | Verwendung | Wert | AA |
|---|---|---|---|
| `--ink` #15181B auf `--canvas` #F2F1ED | Fließtext, Überschriften | 15,8 : 1 | ja |
| `--text-secondary` #6A6E72 auf `--canvas` | Mono-Labels, Kicker, Hinweise | 4,55 : 1 | ja (Grenze, deshalb nie unter 11 px und nie mit Deckkraft) |
| `--accent` #2A5B65 auf `--canvas` | Textlinks, aktiver Zustand, Fokus | 6,7 : 1 | ja |
| `--accent-hover` #1E454D auf `--canvas` | Hover der Textlinks | 9,2 : 1 | ja |
| `--on-dark` #F2F1ED auf `--ink` | Archiv, Namen | 15,8 : 1 | ja |
| `--on-dark-secondary` #A9ADB1 auf `--ink` | Archiv, Nummern, Ort · Status, Filter | 7,9 : 1 | ja |
| #8FC0CA auf `--ink` | aktiver Filter im Archiv, Kartenquadrat warm | 9,0 : 1 | ja |
| `--accent-muted` #C6D2D5 auf `--ink` | Haarlinien im Archiv (nicht Text) | 11,5 : 1 | – |
| Weiß #F2F1ED über dem Film, schlechtester 2-Prozent-Bereich je Band | Kopf, Band 1 bis 4 | 4,93 / 5,28 / 5,89 / 5,72 : 1 | ja (Ziel 4,5) |
| `.fehlt` #6A6E72 mit Deckkraft .55 auf `--canvas` | Platzhalter `[[FEHLT]]` | etwa 2,3 : 1 | nein, bewusst: ist kein Inhalt, sondern die Markierung einer Lücke; verschwindet, sobald der Wert eingetragen ist |

Lighthouse 13.4 (Chrome 152 headless, lokaler Server mit gzip wie bei GitHub Pages):
mobil Leistung 99, Barrierefreiheit 100, Best Practices 100, SEO 100; LCP 2,1 s simuliert (Ziel 2,0 s, knapp verfehlt;
beobachtet 0,15 s), CLS 0, TBT 0 ms. Desktop 100 / 100 / 100 / 100, LCP 0,5 s.
