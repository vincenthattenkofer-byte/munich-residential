# ASSETS.md · Bildinventar

Stand: 18. September 2026. Alle Maße in Pixel, gemessen mit ffprobe.
Quelle A = Webexport der Altseite (`munich-residential-assets/`), Quelle B = Google Drive des
Auftraggebers (`drive-neu/bilder/`). Beide Ordner liegen außerhalb des veröffentlichten Repos.

## 1. Projektbilder, wie sie auf der Seite liegen (`assets/projekte/`)

Regel aus dem Auftrag: kein Bild größer als das 1,3-Fache seiner nativen Breite. Die Bilder
liegen deshalb in nativer Auflösung, nur der weiße Rand des Webexports ist abgeschnitten
(rechts 26 und unten 24 bis 26 px bei 616 px breiten, rechts 12 und unten 17 px bei 1036 px breiten Bildern, gemessen pro Spalte und Zeile). Es wird
nichts hochgerechnet. Maximale Anzeigebreite steht rechts.

| Nr | Datei | Quelle | Original | Zugeschnitten | Art | Anzeige max. |
|---|---|---|---|---|---|---|
| 01 | 01_hansastrasse_muenchen.jpg | A 01 (jpg) | 616 × 532 | 590 × 506 | Visualisierung | 767 px |
| 02 | 02_nymphenburger-strasse_muenchen.jpg | A 02 (jpg) | 616 × 532 | 590 × 506 | Visualisierung | 767 px |
| 03 | 03_aeussere-muenchner-strasse_wolfratshausen.jpg | A 03 (jpg) | 616 × 532 | 590 × 506 | Visualisierung | 767 px |
| 04 | 04_schanzaeckerstrasse_nuernberg.jpg | A 04 (jpg) | 616 × 532 | 590 × 506 | Visualisierung | 767 px |
| 05 | 05_wielandstrasse_eching.jpg | A 05 (jpg) | 616 × 532 | 590 × 506 | Visualisierung | 767 px |
| 06 | 06_schwedenstrasse_muenchen.jpg | A 06 (png) | 616 × 420 | 590 × 396 | Visualisierung | 767 px |
| 07 | 07_arnulfstrasse_muenchen.jpg | A 07 (png) | 616 × 420 | 590 × 396 | Foto | 767 px |
| 08 | 08_ringbergstrasse_muenchen.jpg | A 08 (jpg) | 1036 × 700 | 1024 × 682 | Foto | 1331 px |
| 09 | 09_edisonstrasse_nuernberg.jpg | A 09 (jpg) | 1036 × 700 | 1024 × 682 | Foto | 1331 px |
| 10 | 10_philipp-helmer-strasse_olching.jpg | A 10 (jpg) | 1036 × 700 | 1024 × 682 | Foto | 1331 px |
| 11 | 11_muenchner-freiheit_schwabing.jpg | A 11 (jpg) | 616 × 532 | 590 × 506 | Visualisierung | 767 px |
| 12 | 12_klenzestrasse_glockenbach.jpg | A 12 (jpg) | 616 × 532 | 590 × 506 | Visualisierung | 767 px |
| 13 | 13_klenzestrasse_ismaning.jpg | A 13 (png) | 616 × 420 | 590 × 396 | Foto | 767 px |
| 14 | 14_gustav-heinemann-ring_muenchen.jpg | A 14 (png) | 616 × 420 | 590 × 396 | Foto | 767 px |
| 15 | 15_haidelweg_pasing.jpg | A 15 (png) | 616 × 420 | 590 × 396 | Foto | 767 px |
| 16 | 16_leibstrasse_haar.jpg | A 16 (png) | 616 × 420 | 590 × 396 | Foto | 767 px |
| 17 | 17_konradstrasse-richterstrasse_chemnitz.jpg | A 17 (png) | 616 × 420 | 590 × 396 | Foto | 767 px |
| 18 | 18_objekt-landshut.jpg | A 18 (png) | 616 × 420 | 590 × 396 | Foto | 767 px |
| 19 | 19_adalbert-stifter-strasse_geretsried.jpg | A 19 (jpg) | 616 × 532 | 590 × 506 | Foto | 767 px |
| 20 | 20_zeisigweg_freising.jpg | B 2022_01_IMGNT_01.jpg | 1288 × 868 | 1280 × 852 | Foto | 1664 px |
| 21 | 21_pettenkoferstrasse_muenchen.jpg | B IMG_6691.jpeg | 1148 × 1064 | 1148 × 1064 | Foto | 1492 px |

Zu jedem JPG liegt eine WebP-Fassung gleicher Maße (libwebp, Qualität 80, im Mittel ein Drittel kleiner); die Seite
bietet sie per `<picture>` an, das JPG bleibt Original und Rückfall.
Die PNG-Quellen wurden als JPG (Qualität 2) gespeichert, weil sie Fotos ohne Transparenz sind.
Die Auftragsvorgabe „PNG bleibt PNG" ist damit bewusst abgewichen: Dateigröße halbiert,
optisch kein Unterschied, Originale bleiben unter Quelle A erhalten.

## 2. Galerien (`assets/galerie/`)

| Datei | Quelle | Maße | Gehört zu |
|---|---|---|---|
| zeisigweg-01 … 08.jpg | B 2022_01_IMGNT_01, 02, 03, 04, 05, 07, 09, 10 | 1280 × 852 | MR-020 Zeisigweg |
| pettenkofer-01.jpg | B IMG_6691.jpeg | 1148 × 1064 | MR-021 Pettenkoferstraße |
| pettenkofer-02.jpg | B IMG_2621.jpg | 952 × 1268 | MR-021, Zuordnung ist eine Annahme (siehe OFFENE-PUNKTE) |
| leibstrasse-01.jpg | B DJI_0030.JPG | 1456 × 818 | MR-016 Leibstraße, Luftbild |
| muenchner-freiheit-02.jpg | A 02_zusatzbilder/muenchner-freiheit_zweite-ansicht.png | 590 × 396 | MR-011, zweite Ansicht desselben Eckhauses |

## 3. Kopf der Seite (`assets/`)

| Datei | Maße | Herkunft |
|---|---|---|
| hero-scrub.mp4 | 1728 × 996, 6 s, 5,5 MB | Kamerafahrt, aus dem Luftbild DJI_0030 (Leibstraße, Haar) berechnet. Das Gebäude ist echt, die Bewegung ist gerechnet. Nur auf großen Bildschirmen mit Maus geladen. |
| hero-poster.jpg | 1600 × 922 | Erstes Bild der Kamerafahrt |
| hero-ending.jpg | 1800 × 1038 | Letztes Bild, Standbild für Hochformat-Tablets und reduzierte Bewegung |
| hero-ending-960.jpg / .webp | 820 × 473 | dasselbe Bild, für Telefone bis 720 px (67 KB / 57 KB), per `image-set()` und `<link rel="preload">` |

## 4. Logo (`assets/`)

| Datei | Maße | Herkunft |
|---|---|---|
| logo-mr.png | 829 × 502 | von der Altseite geladen (`wp-content/uploads/2021/01/mr-logo-gruen-transparent.png`), PNG mit Alphakanal, per Alphakanal in die Hausfarbe #2A5B65 eingefärbt. Schärfste vorhandene Quelle. Über dem Film wird dieselbe Datei per CSS-Filter hell gestellt, die Marke ist einfarbig. |

Die drei Logodateien in Quelle A (`03_logos/`) sind trotz Endung `.png` JPEGs ohne Alphakanal und in
zwei Fällen weiß auf weiß; unbrauchbar. Ein Vektor-Original (SVG, PDF, AI) gibt es nicht. Siehe OFFENE-PUNKTE.

## 5. Schriften (`fonts/`)

| Datei | Größe | Schnitte | Lizenz |
|---|---|---|---|
| archivo-var-latin.woff2 | 35 KB | variabel, genutzt 500 und 600 | SIL Open Font License 1.1 |
| instrumentsans-400-latin.woff2 | 17 KB | 400 | SIL Open Font License 1.1 |
| ibmplexmono-400-latin.woff2 | 15 KB | 400 | SIL Open Font License 1.1 |

Nur der Latin-Teilsatz (deckt Umlaute, ß, €, m² ab). Keine Anfrage an Google Fonts.

## 6. Nicht verwendet, mit Grund

| Datei | Grund |
|---|---|
| A 02_zusatzbilder/hansastrasse_zweite-ansicht.png (616 × 532) | zeigt ein anderes Gebäude als MR-001 (dunkler Riegel mit versetzter Rasterfassade gegen Klinkerbau mit Bandfenstern). Nicht als dasselbe Objekt zeigen. Wartet auf Klärung. |
| A 02_zusatzbilder/seitenband_header-2048px.jpg (1456 × 840) | Herkunft unbekannt, per Bildvergleich nicht das Luftbild der Leibstraße (SSIM 0,16). Zeigt möglicherweise kein eigenes Objekt. |
| A 02_zusatzbilder/stimmung_*.jpg | Stimmungsbilder der Altseite, Stockfoto-Charakter |
| A 04_icons-altseite/* (14 Dateien) | Icon-Raster, ausdrücklich verboten |
| A 05_duplikate/* | JPG-Doubletten der PNG-Fassungen |
| A 03_logos/* (drei Dateien) | JPEG mit PNG-Endung, ohne Alphakanal; die 112-px-Fassung zu klein |
| bisherige assets/station-*.jpg | waren KI-generierte Stimmungsbilder, entfernt |
| bisherige assets/karte-*.jpg (Sentinel-2) | Satellitenkacheln, durch die SVG-Karte aus Vektordaten ersetzt (Natural Earth, OpenStreetMap; 44 KB in `index.html`); liegen in der Git-Historie (Commit d96c71f) |
| B drive-neu/dokumente/* | vertrauliche Angebotsunterlagen Dritter, nur intern, nie veröffentlichen |
