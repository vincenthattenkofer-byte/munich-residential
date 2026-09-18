# Munich Residential

Website der Munich Residential GmbH, Pöcking bei München. Ein Werkverzeichnis mit 21 Objekten.

Statische Seite: eine `index.html` mit eingebettetem CSS und JavaScript, dazu `assets/` (Bilder,
Film) und `fonts/` (drei WOFF2). Kein Framework, kein Build-Schritt, keine Anfrage an fremde
Server. Läuft per Doppelklick auf `index.html` und auf jedem einfachen Webspace.

## Ändern und veröffentlichen

Objekte stehen in `index.html` im Feld `PROJEKTE` (Name, Ort, Status, Koordinaten, Bild, Galerie,
Fakten). Fehlende Fakten stehen als `null` und erscheinen auf der Seite als `[[FEHLT: …]]`.

    git add -A
    git commit -m "Was geändert wurde"
    git push

GitHub Pages stellt die Änderung nach etwa einer Minute live.

## Dokumente

- `AUDIT.md`: Bestandsaufnahme der alten Fassung, 44 Punkte mit Fundstelle
- `PLAN.md`: wie jeder Abschnitt gebaut ist und warum
- `ASSETS.md`: Bildinventar mit Quelle, Maßen und Anzeigegrenze
- `CHANGELOG.md`: was sich geändert hat
- `OFFENE-PUNKTE.md`: was der Auftraggeber liefern oder entscheiden muss

## Bildnachweis

Das Bild im Kopf der Seite zeigt das Objekt Leibstraße in Haar; die Kamerafahrt wurde aus dem
Luftbild berechnet. Alle Projektbilder zeigen echte Objekte oder deren Visualisierung, so
gekennzeichnet. Lageplan: Grenzen, Flüsse und Seen aus Natural Earth (gemeinfrei), Stadtgrenze, Isar
und Mittlerer Ring aus OpenStreetMap (© OpenStreetMap-Mitwirkende, ODbL). Schriften: Archivo,
Instrument Sans, IBM Plex Mono (SIL Open Font License).
