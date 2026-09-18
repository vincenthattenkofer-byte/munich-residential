# PLAN.md · Wie jeder Abschnitt neu wird, und warum

Richtung B. Eine `index.html`, alles eingebettet, Schriften aus `fonts/`. Kein Framework, kein
Build, keine Fremdanfrage. Läuft per Doppelklick.

## Grundsätze

- **Ein Werkverzeichnis, keine Broschüre.** Jede Zahl steht in Mono, jede Zeile hat eine
  Nummer. Was nicht bekannt ist, steht als `[[FEHLT: …]]` da, gedämpft, aber sichtbar.
- **Sieben Abschnitte, sieben Skelette.** Kein Abschnitt hat denselben Aufbau wie sein Nachbar.
  Kopf: Film über volle Fläche, Text links unten. Haus: zwei Spalten und eine Linie. Arbeiten:
  dunkle Fläche, Liste links, Karte rechts. Weg: eine gezeichnete Linie quer über die Seite.
  Ankauf: ein Satz auf voller Breite, darunter eine Mono-Zeile. Fragen: Einspalter aus
  Haarlinien. Kontakt: Formular rechts, Anschrift links (gespiegelt zum Haus).
- **Der Akzent erscheint viermal**: aktiver Filter, Fokus, die eine Handlungsaufforderung
  (als Textlink mit Unterstrich, nicht als Fläche), der vollendete Halte-Zustand.
- **Bewegung: eine Kurve `cubic-bezier(.2,.7,.1,1)`**, 400 bis 900 ms, nur `transform`,
  `opacity`, `clip-path`. Einmal, ruhig, nie federnd. Bilder kommen per `clip-path`-Aufzug.
- **Bilder in nativer Größe.** Bildspalte höchstens 1,3 × native Breite, sonst Leerraum.

## Kopf

Bleibt ein Scroll-Film nach der Bandtabelle aus `design-package.md` (600vh, vier Bänder,
Blob-Laden, dt-normierte Interpolation, gesperrte Seeks). Weg damit: Ladering, Textschatten,
`!important`. Der Scrim allein trägt die Lesbarkeit; nachgemessen auf dem ungünstigsten Bild
jedes Bandes, Ziel 4,5 : 1. Fünf statische Tore identisch in CSS und JS. Statisch: das Endbild,
Titel „Der Abschluss hält.", Subline, Textlink „Grundstück anbieten". Der Film ist aus einem
echten Luftbild gerechnet; der Fuß sagt das.

## Navigation

Wortmarke links (das echte Logo, aus der schärfsten Quelle in die Hausfarbe gefärbt; über dem
Film die weiße Fassung), vier Textlinks rechts. Haarlinie erst nach dem Scrollen. Mobil das Wort
„Menü", das ein Vollflächenmenü mit großen Archivo-Zeilen öffnet, Fokus gefangen, Escape schließt.
Skip-Link auf `#main`. Nach jedem Ankersprung wird der Fokus auf den Abschnitt gesetzt.

## Das Haus

Links drei kurze Absätze (der Verbatim-Satz zuerst), rechts eine schmale Mono-Spalte mit den
sechs Kennzahlen als Zeilen mit Haarlinien, nie als Kacheln. Darunter die Zeitleiste: eine
einzige horizontale Haarlinie 2007 bis heute, Jahresmarken in Mono, horizontal scrollbar, per
Pfeiltasten bedienbar. Projekte sitzen auf der Linie, sobald ihr Jahr bekannt ist; bis dahin
stehen sie gesammelt am rechten Ende unter „Jahr offen". Keine erfundenen Jahre.

## Arbeiten

Dunkle Fläche (`--ink`), heller Text. Zwei Spalten: links die Liste, rechts (klebend) die Karte.

- **Liste:** je Zeile `MR—001` in Mono, Name groß in Archivo, darunter Ort · Status in
  Mono-Versalien, Haarlinien dazwischen. Auf Touch-Geräten steht das Bild in der Zeile.
- **Filter** als Textlinks: Alle · Im Bau · In Planung · Fertiggestellt, dazu Orte. Aktiv = Unter-
  streichung im Akzent. Wechsel per FLIP: Zeilen gleiten auf ihren neuen Platz, nichts springt.
- **Zeigervorschau:** bei Maus folgt ein Bild dem Zeiger mit Trägheit (`translate3d`, Faktor
  0,12 pro Frame, `requestAnimationFrame`), Bild in nativer Größe.
- **Ansichten:** Liste oder Raster, Umschalter in Mono. Raster: Bilder in nativer Breite in
  einem Raster mit viel Leerraum.
- **Tastatur:** Pfeil auf und ab wandern durch die Liste, Enter öffnet.
- **Karte:** selbst gezeichnete SVG, stark abstrahiert. Deutschland als wenige Linien, die Isar
  als eine Linie, Orte als kleine Quadrate mit Mono-Nummer, Projektion linear aus den echten
  Koordinaten. Zwei Stufen: Deutschland, dann München und Umland (Klick oder Taste).
  Hover auf der Karte hebt die Listenzeile hervor, Hover auf der Zeile das Quadrat. Kein
  Kartendienst, keine Kacheln.

## Projektansicht

Eigene Adresse `#/arbeiten/<slug>`. Öffnet als Vollflächen-Ansicht über der Seite: Bild oder
Bildfolge links (native Größe, Pfeile, Tastatur, Wischen), rechts das Mono-Datenblatt (Ort,
Nutzung, Status, Jahr, Fläche, Einheiten, Architekt; Unbekanntes als `[[FEHLT]]`), darunter
zwei bis drei Sätze, nur wo belegt. Vor und Zurück zum nächsten Projekt, Escape schließt,
Browser-Zurück funktioniert, Fokus wird gefangen und zurückgegeben, Hintergrund `inert`.
Übergang per View Transitions API mit Fallback auf Opacity.

## Vom Grundstück zur Übergabe

Drei Stationen auf einer handgezeichneten SVG-Linie quer über die Seite, ohne Fotos (die
alten waren KI-Bilder). Verbatim-Texte. Die Halten-Interaktion zeichnet die Linie; loslassen
lässt sie zurückgleiten, vollendet leuchten die drei Stationen nacheinander im Akzent und der
Zustand bleibt. Reduzierte Bewegung: sofort der Endzustand.

## Ankaufsprofil, Fragen, Kontakt

Ankauf: der Verbatim-Absatz als Lede über volle Breite, darunter die Mono-Liste als eine Zeile
mit Trennpunkten (auf schmalen Bildschirmen untereinander). Fragen: `<details>` mit
Haarlinien, Marker ist das Wort „Antwort" in Mono statt eines Plus. Kontakt: Anschrift links in
Mono, Formular rechts mit sichtbaren Labels und Unterstrich-Feldern, Versand per `mailto:`,
ehrliche Erfolgsmeldung (verbatim).

## Fuß, Impressum, Datenschutz

Fuß: vier Spalten Mono (Anschrift, Kontakt, Rechtliches, Bildhinweis), Jahr per Skript.
Impressum und Datenschutz als Ansichten `#/impressum` und `#/datenschutz` in derselben Datei,
Unbekanntes als `[[FEHLT: …]]`. Unbekannte Hash-Adresse: eigene 404-Ansicht mit Rückweg.

## Technik

- Schriften: drei WOFF2 in `fonts/`, `font-display: swap`, Ersatzschrift mit `size-adjust`,
  `<link rel="preload">` für die Display-Schrift.
- Bilder: `width`/`height`, `loading="lazy"` unter dem ersten Bildschirm, `decoding="async"`,
  beschreibende `alt`-Texte.
- `overflow-x: clip` auf `html` und `body`, Touch-Ziele 44 px, `:focus-visible` im Akzent,
  eine `h1`, Landmarken, Überschriftenfolge.
- SEO: Titel, Beschreibung, kanonische Adresse, Open Graph mit `<!-- DEPLOY STEP -->`,
  JSON-LD `Organization`, Inline-SVG-Favicon, `lang="de"`.
- Druck: das Archiv druckt als Werkverzeichnis auf A4, Film und Karte entfallen.
- JS: eine IIFE, keine globalen Variablen, Seite ohne JS vollständig lesbar (Liste, Texte,
  Formular, Impressum als Abschnitte sichtbar).
- Prüfungen: Screenshots 375/1440/1920 je Abschnitt, zwei Kritikdurchgänge, Tastatur,
  reduzierte Bewegung, ohne JS, Lighthouse mobil, HTML-Validierung, grep-Gate.

## Reihenfolge der Arbeit

1. Bilder in nativer Größe schneiden, Logo einfärben, KI- und Kartenkacheln entfernen. Commit.
2. Gerüst: Head, Schriften, Tokens, Nav, Kopf. Commit.
3. Haus mit Zeitleiste. Commit.
4. Arbeiten: Liste, Filter, Vorschau, Raster, Tastatur, Karte. Commit.
5. Projektansicht mit Routing. Commit.
6. Weg, Ankauf, Fragen, Kontakt, Fuß, Impressum, Datenschutz, 404. Commit.
7. Gesamtdurchgang, Lighthouse, Validierung, grep. CHANGELOG, OFFENE-PUNKTE. Commit.
