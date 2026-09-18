# OFFENE-PUNKTE.md · Was der Auftraggeber liefern oder entscheiden muss

Stand: 18. September 2026. Alles, was auf der Seite als `[[FEHLT: …]]` steht, ist hier gesammelt.
Nichts davon wurde erfunden oder geschätzt.

## A. Rechtlich, vor dem Betrieb unter munich-residential.com zwingend

1. **Impressum:** Geschäftsführung (Vor- und Nachname), Registergericht und HRB-Nummer,
   Umsatzsteuer-Identifikationsnummer, Verantwortlicher nach § 18 Abs. 2 MStV.
2. **Datenschutz:** Hosting-Anbieter nach dem Umzug (derzeit GitHub Pages, GitHub Inc.),
   Speicherdauer der Server-Protokolle, ob eine Datenschutzbeauftragte Person benannt ist.
3. **Bildrechte:** Urheber der Fotos (Dateinamen der Altseite deuten auf „M. Mischek 2022")
   und der Visualisierungen (Architekturbüros). Nutzungsrechte für die Website bestätigen.
4. **Adressen im Kopf der Datei:** `<!-- DEPLOY STEP -->` in `index.html` markiert die vier
   Stellen (canonical, og:url, og:image, JSON-LD), die beim Domainwechsel geändert werden.

## B. Fakten zu den 21 Objekten

Für jedes Objekt fehlen im Datenblatt: **Nutzung, Fertigstellungsjahr, Fläche, Einheiten,
Architekturbüro.** Stichpunkte genügen; sie werden in `PROJEKTE` in `index.html` eingetragen
(Felder `nutzung`, `jahr`, `flaeche`, `einheiten`, `architekt`). Sobald ein `jahr` gesetzt ist,
rückt das Objekt automatisch auf die Zeitleiste im Abschnitt „Das Haus".

5. **Status ist eine Annahme:** Visualisierung = Im Bau oder In Planung, Foto = Fertiggestellt.
   Besonders prüfen: Äußere Münchner Straße (Wolfratshausen), Schanzäckerstraße (Nürnberg),
   Wielandstraße (Eching), Schwedenstraße (München), Pettenkoferstraße (aus dem Foto als
   „Im Bau" eingestuft: Baustellenboden, Paletten).
6. **Hansastraße:** Zwei Bilder der Altseite zeigen zwei verschiedene Gebäude (Klinkerbau mit
   Fensterbändern gegen dunklen Riegel mit versetzter Rasterfassade). Die zweite Ansicht ist
   deshalb nicht auf der Seite. Ist es ein zweites Projekt? Dann Name, Ort, Status.
7. **IMG_2621** (Altbaustraße mit Baukran) ist als zweites Bild der Pettenkoferstraße
   eingesetzt. Das ist eine Annahme aus der Bildreihe im Drive. Bitte bestätigen oder streichen.
8. **Zeisigweg:** Die acht Aufnahmen tragen das Datum Januar 2022. Was wurde dort gemacht
   (Neubau, Sanierung, Bestand)? Der Text sagt derzeit nur, was das Bild zeigt.
9. **Objekt Landshut** hat keinen Straßennamen. Ringbergstraße ist per Adresssuche in
   München-Ramersdorf verortet; bitte bestätigen.
10. **Nutzung** lässt sich bei den Gewerbebauten (Arnulfstraße, Edisonstraße, Philipp-Helmer-
    Straße) aus dem Bild vermuten, steht aber bewusst als offen da.

## C. Bilder

11. **Originalauflösungen.** 14 der 19 Altbilder sind 590 px breit. Die Seite zeigt sie deshalb
    nie größer als 767 px. Wer schärfere Fassungen hat (Fotograf, Architekturbüro, Präsentations-
    PDF der Hansastraße), liefert sie in den Ordner `assets/projekte/` unter demselben Dateinamen;
    die Maße `w`/`h` in `PROJEKTE` werden dann angepasst.
12. **Logo:** Die schärfste Fassung stammt von der Altseite (829 × 502 px, PNG mit Alphakanal) und
    wurde in die Hausfarbe #2A5B65 eingefärbt. Das Original ist ein leicht anderes Petrol.
    Eine Vektordatei (SVG, PDF, AI) wäre für scharfe Darstellung auf allen Bildschirmen besser.
13. **Kopf der Seite:** Die Kamerafahrt wurde mit einem Bildmodell aus dem echten Luftbild der
    Leibstraße berechnet (Entscheidung des Auftraggebers: „Euer echtes Luftbild beleben"). Der
    Auftrag verbietet KI-Bilder; die Fahrt ist eine Grauzone, weil Gebäude und Aufnahme echt sind
    und nur die Bewegung gerechnet ist. Der Fuß der Seite sagt das offen. Wer das nicht will:
    `VIDEO_URL` in `index.html` leeren, dann steht überall das Endbild (das echte Luftbild).
14. **seitenband_header-2048px.jpg** aus dem Altbestand (1456 × 840) zeigt ein unbekanntes
    Objekt. Nicht verwendet. Falls es ein eigenes Projekt ist: Name, Ort, Status.

## D. Entscheidungen, die ich getroffen habe (bitte gegenlesen)

15. **21 statt 19 Objekte.** Der Auftrag nennt 19; Zeisigweg (Freising) und Pettenkoferstraße
    (München) kamen mit echten Fotos aus dem Drive dazu und sind im Verzeichnis MR—020 und MR—021.
16. **Karte aus echten Geodaten, ohne Kartendienst.** Grenzen, Bundesländer, Flüsse und Seen aus
    Natural Earth (gemeinfrei), Stadtgrenze München, Isar und Mittlerer Ring aus OpenStreetMap
    (ODbL, Nennung im Fuß). Alles liegt als vereinfachte Vektoren in der Datei (44 KB), beim Laden
    wird nichts nachgeladen. Die frühere Fassung mit Sentinel-2-Kacheln liegt in der Git-Historie
    (Commit d96c71f). Die Objektpunkte sitzen auf echten Koordinaten aus der Adresssuche.
17. **PNG-Quellen als JPG.** Sieben Altbilder lagen als PNG vor, sind aber Fotos ohne Transparenz.
    Sie liegen jetzt als JPG (halbe Dateigröße, gleiche Qualität). Die Originale bleiben in
    `munich-residential-assets/`.
18. **Fuß-Satz zum Kopfbild** weicht vom Verbatim in `design-package.md` ab („ist eine
    Visualisierung"), weil der Kopf inzwischen das echte Objekt zeigt. Der neue Satz ist der ehrliche.
19. **Stationen ohne Fotos.** Die drei Bilder im Abschnitt „Vom Grundstück zur Übergabe" waren
    KI-Stimmungsbilder und sind entfernt. Die Stationen stehen auf der gezeichneten Linie.
20. **Kein Deutsch/Englisch-Umschalter.** Alle Texte sind verbatim deutsch festgelegt; eine
    englische Fassung wäre Übersetzungsarbeit mit Freigabe und kommt, wenn gewünscht, als
    zweites Textobjekt im Skript.
21. **Kontaktformular per mailto.** Es gibt keinen Server. Der Knopf öffnet das E-Mail-Programm
    des Besuchers; die Seite sagt das. Wer echte Formularannahme will, braucht einen Dienst
    (Formspark, eigenes Skript) und dann einen Datenschutzabsatz dazu.
22. **Projektansichten brauchen Skript.** Ohne JavaScript ist das Verzeichnis mit Bildern lesbar,
    die Einzelansicht mit Datenblatt öffnet aber nicht (es gibt nur eine Datei).
