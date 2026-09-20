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
- Lighthouse gegen die Live-Seite (GitHub Pages): mobil 99 / 100 / 100 / 100, LCP 1,8 s, CLS 0; Desktop 100 / 100 / 100 / 100.
  Das Formular trägt keine mailto-Action mehr im Markup, Chrome wertete sie als Mixed Content; der Versand läuft über das Skript.
- html-validate ohne Befund. grep: 0 Gedankenstriche außer `MR—0xx`, 0 Wörter der Verbotsliste,
  0 Ausrufezeichen, 0 `!important`, 0 Schatten, 0 Rundungen, eine `h1`.

### Zweite Runde (18. September 2026, Abend)
- **Bildband:** bildschirmbreite, seitlich scrollende Bildstrecke mit elf Aufnahmen zwischen „Das Haus“
  und „Arbeiten“; ziehen, Pfeiltasten, zwei Textknöpfe; Klick öffnet das Objekt.
- **Raster als Startansicht** im Verzeichnis, die Liste ein Klick entfernt; das Bildpanel gilt nur der Liste.
- **Eigene Seite je Objekt** unter `arbeiten/<slug>/` mit Titel, Beschreibung und Vorschaubild für
  WhatsApp, LinkedIn und Suchmaschinen; leitet Menschen in die Projektansicht, Maschinen lesen die Seite.
  Dazu `sitemap.xml`, `robots.txt` und „Link kopieren“ in der Projektansicht.
- **Register nach Orten und Stand** ersetzt die Zeitleiste, solange keine Fertigstellungsjahre vorliegen;
  Klick filtert das Verzeichnis. Die Zeitleiste erscheint automatisch, sobald ein Jahr eingetragen ist.
- **Englische Fassung:** Umschalter EN/DE in Leiste und Menü, alle Texte übersetzt (Rechtstexte bleiben
  deutsch, mit Hinweis), Wahl gespeichert, Browsersprache als Vorgabe beim ersten Besuch.

### Dritte Runde (20. September 2026): Kopf auf dem Telefon
- Auf Telefonen und Hochformat-Tablets stand im Kopf bisher nur ein Standbild mit dem letzten
  Satz. Jetzt laufen dort **dieselben vier Sätze als Scroll-Folge** wie am Desktop: das Bild
  bleibt stehen und wächst über den ganzen Weg um neun Prozent, die Sätze ziehen darüber durch.
  Kein Film, kein zusätzlicher Ladeaufwand (gemessen: null Videoabrufe auf dem Telefon).
- Der Abdunkler über dem Bild dreht sich mit: am Desktop läuft er durch die linke Textbahn,
  auf dem Telefon von unten nach oben, weil der Text dort unten steht. Nachgemessen, schlechtester
  Bereich je Satz: 10,96 / 9,08 / 8,61 / 5,10 zu 1 auf dem Telefon (Vorgabe 4,5).
- Hinweis „Weiter scrollen“ unten rechts, verschwindet nach der ersten Bewegung.
- Die fünf Tore sind jetzt zwei Gruppen: Tor 1 bis 4 schalten auf die Folge ohne Film,
  Tor 5 (reduzierte Bewegung) weiterhin auf den starren Kopf mit einem Satz. Ohne Skript
  bleibt es ebenfalls beim starren Kopf.

### Dokumente
- `ASSETS.md`, `AUDIT.md` (44 Punkte), `PLAN.md`, `OFFENE-PUNKTE.md`, `CHANGELOG.md`.
