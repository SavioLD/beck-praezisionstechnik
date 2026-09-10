# Beck Präzisionstechnik – Karriereseite

Recruiting-Landingpage für die **Beck Präzisionstechnik GmbH & Co. KG** (Oberndorf am Neckar).
Stelle: **Kurzdreher / Maschineneinrichter (m/w/d)** (eine Position).

Aufbau 1:1 an der ALWA-Karriereseite orientiert – im Beck-CI (Steel-Blue).
Self-contained, keine Build-Schritte.

## Inhalt

- `index.html` – die komplette Seite (self-contained, kein Build nötig)
- `supabase-bewerbungen.sql` – legt den Storage-Bucket für den optionalen Lebenslauf-Upload an
- `bilder/` – Hero-Fotos (optional, siehe unten)
- `creatives/` – META-Ads-Creatives (4:5 Feed + 9:16 Story), zwei Motiv-Varianten
- `.nojekyll` – sorgt dafür, dass GitHub Pages die Dateien 1:1 ausliefert

## Bilder (Hero-Fotos & Logo)

Die Fotos liegen im Ordner **`bilder/`**. Der Hero lädt automatisch das passende
Bild – fehlt es, bleibt der Beck-Farbverlauf stehen (kein kaputtes Bild).
Aktuelle Zuordnung (in `index.html`, Objekt `HERO_IMG`):

- allgemein (ohne Stellen-Parameter) → `bilder/MS52.jpg` (Sechsspindler)
- `?stelle=maschineneinrichter` → `bilder/Hohlschraube.jpg`
- `?stelle=kurzdreher` → `bilder/Steuerboden.jpg`

Zum Tauschen einfach die Dateinamen im Objekt `HERO_IMG` anpassen. Querformat,
Motiv möglichst mittig/rechts – links liegt die Textfläche.

Das offizielle Beck-Logo (`bilder/Logo2012.jpg.JPG`) wird oben in der Topbar
angezeigt. Hero und Footer nutzen bewusst den weißen „BECK"-Schriftzug (klar
lesbar auf dunklem Grund).

## Deeplinks für die Ad

Es gibt **eine** Stelle (Kurzdreher / Maschineneinrichter). Der optionale
`?stelle=`-Parameter beworbt nichts anderes – er steuert nur das passende
**Hero-Foto** zum Anzeigenmotiv:

- `…/?stelle=maschineneinrichter` → Hero-Foto Hohlschraube
- `…/?stelle=kurzdreher` → Hero-Foto Steuerboden
- ohne Parameter → Hero-Foto MS52 (Sechsspindler)

## Vorfilterung (Screening)

Vor den Kontaktdaten beantworten Bewerber **4 kurze Qualifizierungsfragen**:
Qualifikation, Erfahrung an CNC-Dreh-/Mehrspindelautomaten, Schichtbereitschaft
und Erreichbarkeit des Standorts. Jede Antwort bringt 0–3 Punkte (max. 12).

Wer den Mindest-Score unterschreitet (Standard `SCREEN_MIN_SCORE = 3`, d. h.
rundum die schlechtesten Antworten), wird **freundlich abgelehnt – es geht KEIN
Lead an Leadtable**. So kommen nur vorqualifizierte Bewerbungen bei euch an.

- Strenger/lockerer filtern: `SCREEN_MIN_SCORE` in `index.html` anpassen
  (z. B. 5 oder 6 = strenger).
- Die Punktzahl steht bei jedem Lead im Feld `eignung_punkte` (z. B. „8 / 12").
- Screen-out und Erfolg gelten nur für den aktuellen Besuch – ein Seiten-Neuladen
  startet frisch.

## Bewerbungen (Leadtable)

Jede abgeschlossene Bewerbung wird per Webhook an Leadtable gesendet. Felder:
`vorname`, `nachname` (Name wird nur **einmal** übergeben – kein zusätzliches
kombiniertes `name`-Feld), `telefon`, `email`, `stelle`, `qualifikation`,
`cnc_erfahrung`, `schicht`, `erreichbarkeit`, `eignung_punkte`, `lebenslauf`,
`quelle`, `seite`. Der Webhook ist in `index.html` in der Variable `WEBHOOK_URL`
hinterlegt und zeigt auf die Beck-Kachel in Leadtable.

## Lebenslauf-Upload (optional, standardmäßig aus)

Der optionale Datei-Upload nutzt Supabase Storage (Bucket `bewerbungen`). Er ist
**deaktiviert**, bis ein eigenes Beck-Supabase-Projekt hinterlegt ist – bis dahin
geht die Bewerbung trotzdem an Leadtable (Feld `lebenslauf` = „wird nachgereicht“).

Zum Aktivieren:

1. In `index.html` `SUPABASE_URL` und `SUPABASE_KEY` (publishable/anon key) eintragen.
2. Einmalig `supabase-bewerbungen.sql` im Supabase-SQL-Editor ausführen – legt den
   Bucket `bewerbungen` an. Danach landet im Leadtable-Feld `lebenslauf` ein direkt
   öffenbarer Link.

## Live schalten (GitHub Pages)

1. Repo-Settings → **Pages** → Source: **Deploy from a branch**, Branch: `main` / `/root`.
2. Nach ein paar Minuten ist die Seite unter `https://<user>.github.io/beck-praezisionstechnik/`
   erreichbar (bzw. unter der hinterlegten Custom-Domain).

## Lokal anschauen

```bash
python3 -m http.server 8000
# → http://localhost:8000
```
