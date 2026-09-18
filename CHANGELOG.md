# CHANGELOG.md

## 2026-09-18 · Komplettüberarbeitung (Branch `ueberarbeitung`, auf `main` veröffentlicht)

### Entfernt
- Google Fonts. Drei WOFF2 liegen in `fonts/`, Ersatzschriften mit `size-adjust`.
- Drei KI-generierte Stationsbilder, fünf Satellitenkacheln (1,3 MB), Ladering, Textschatten,
  Hover-Zoom auf Bildern, pulsierende Kartenpunkte, Plus-Icons, Vollbild-Icon, gefüllte Buttons.
- Neun `!important`, alle inline `style`-Attribute außer Bildbreiten als CSS-Variablen.
- Hochgerechnete Projektbilder (1280 px aus 616 px).

### Neu
- **Bilder in nativer Auflösung**, weiße Exportränder abgeschnitten (26/24 px bei 616er,
  12/17 px bei 1036er Bildern, 8/15 px bei den Drive-Fotos). Kein Bild größer als 1,3 × nativ.
- **Logo** aus der Altseite in 829 px mit Alphakanal, in die Hausfarbe gefärbt; über dem Film per
  CSS-Filter hell (eine Datei statt zwei).
- **WebP** zu jedem Projekt- und Galeriebild per `<picture>`, Telefon-Kopfbild in 820 px per
  `image-set()` und Preload. Originale bleiben.
- **Navigation:** Wortmarke, vier Textlinks, Haarlinie erst nach dem Scrollen, aktiver
  Abschnitt unterstrichen, mobil das Wort „Menü" mit Vollflächenmenü (Fokusfang, Escape).
  Skip-Link, Fokus nach Ankersprung auf den Abschnitt.
- **Kopf:** Scroll-Film nach Bandtabelle, ohne Ring und Schatten, Lesbarkeit nachgemessen
  (schlechtester Bereich je Band 4,9 bis 5,9 : 1). Fünf statische Tore identisch in CSS und JS,
  ohne `!important` (Bandregeln ohne ID-Selektoren). Ohne Skript steht das Endbild mit Text.
- **Das Haus:** Text links, Mono-Kennzahlen rechts, darunter Zeitleiste 2007 bis heute als
  eine Haarlinie, horizontal scrollbar, per Pfeiltasten und Ziehen bedienbar. Objekte ohne
  Jahr stehen gesammelt am Ende („Fertigstellungsjahr offen").
- **Arbeiten:** dunkle Fläche. Liste mit `MR—001`, Name, Ort · Status. Filter nach Status und
  Ort, Wechsel per FLIP. Zeigervorschau mit Trägheit (nur Maus). Listen- und Rasteransicht.
  Pfeiltasten wandern, Enter öffnet. SVG-Karte aus echten Geodaten (Deutschland mit Bundesländern,
  Flüssen und Seen; Umland mit Isar, Seen und Stadtgrenze; Stadt mit Stadtgrenze, Isar und
  Mittlerem Ring), Quadrate mit Mono-Nummer, Orientierungsnamen, in drei Stufen. Hover koppelt
  Karte und Liste. Quellen: Natural Earth (gemeinfrei), OpenStreetMap (ODbL), im Fuß genannt.
- **Projektansicht** mit eigener Adresse `#/arbeiten/<slug>`: Bild oder Bildfolge in nativer
  Größe, Mono-Datenblatt mit `[[FEHLT]]`, Vor und Zurück, Escape, Browser-Zurück, Fokusfang,
  `inert` auf dem Rest, View Transitions mit Fallback.
- **Vom Grundstück zur Übergabe:** drei Stationen auf einer gezeichneten Linie, Halten auf dem
  Wort „halten" zeichnet sie, Loslassen lässt sie zurückgleiten, vollendet bleibt sie.
- **Ankaufsprofil** als ein Satz plus eine Mono-Zeile. **Fragen** als `<details>` mit dem Wort
  „Antwort" statt Icon. **Kontakt:** Anschrift links, Formular mit Unterstrich-Feldern rechts,
  mailto, ehrliche Erfolgsmeldung.
- **Fuß** in vier Mono-Spalten, Jahr per Skript, ehrlicher Satz zum Kopfbild.
- **Impressum, Datenschutz, 404** als Ansichten `#/impressum`, `#/datenschutz`, unbekannte
  Adresse. Unbekanntes als `[[FEHLT: …]]`.
- **Technik:** JSON-LD Organization, canonical, Open Graph mit `<!-- DEPLOY STEP -->`, Inline-
  SVG-Favicon, `overflow-x: clip`, Touch-Ziele 44 px, `:focus-visible` im Akzent, eine `h1`,
  Druckansicht als Werkverzeichnis, Randanzeige mit Abschnitt und Nummer, eine Easing-Kurve
  `cubic-bezier(.2,.7,.1,1)`, Dauern 0,4 / 0,6 / 0,9 s, nur transform, opacity, clip-path.
  Reduzierte Bewegung setzt die Dauern auf 0 und die Endzustände, live in beide Richtungen.

### Prüfungen (18. September 2026)
- Screenshots bei 320, 375, 768, 1024, 1440, 1920, 2560 px, je Abschnitt, außerdem ohne Skript,
  mit reduzierter Bewegung, Menü, Projektansicht, Impressum, 404, Karte in drei Stufen, Raster, Druck.
- Interaktionen per CDP: Filter, FLIP, Raster, Karte (0 Überlappungen), Pfeiltasten, Halten
  (Loslassen gleitet zurück, vollendet bleibt), Routen, Escape, `inert`, 404, Auftritte 14/14,
  kein seitliches Scrollen, Konsole leer, keine Fremdanfrage.
- Lesbarkeit im Kopf, schlechtester Bereich je Band: 4,93 / 5,28 / 5,90 / 5,72 : 1.
- Lighthouse (gzip-Server): mobil 99 / 100 / 100 / 100, LCP 2,1 s simuliert, CLS 0; Desktop 100 / 100 / 100 / 100.
- html-validate ohne Befund. grep: 0 Gedankenstriche außer `MR—0xx`, 0 Wörter der Verbotsliste,
  0 Ausrufezeichen, 0 `!important`, 0 Schatten, 0 Rundungen, eine `h1`.

### Dokumente
- `ASSETS.md`, `AUDIT.md` (44 Punkte), `PLAN.md`, `OFFENE-PUNKTE.md`, `CHANGELOG.md`.
