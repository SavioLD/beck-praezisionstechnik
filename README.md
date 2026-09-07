# Beck Präzisionstechnik – Karriereseite

Recruiting-Landingpage für die **Beck Präzisionstechnik GmbH & Co. KG** (Oberndorf am Neckar).
Stellen: **Maschineneinrichter** und **Kurzdreher** (m/w/d).

Aufbau 1:1 an der ALWA-Karriereseite orientiert – im Beck-CI (Steel-Blue) und mit den
Beck-Positionen. Self-contained, keine Build-Schritte.

## Inhalt

- `index.html` – die komplette Seite (self-contained, kein Build nötig)
- `supabase-bewerbungen.sql` – legt den Storage-Bucket für den optionalen Lebenslauf-Upload an
- `bilder/` – Hero-Fotos (optional, siehe unten)
- `creatives/` – META-Ads-Creatives (4:5 Feed + 9:16 Story) je Position
- `.nojekyll` – sorgt dafür, dass GitHub Pages die Dateien 1:1 ausliefert

## Bilder (Hero-Fotos)

Die Fotos gehören in den Ordner **`bilder/`**. Der Hero lädt automatisch das passende
Bild – fehlt es, bleibt der Beck-Farbverlauf stehen (kein kaputtes Bild). Erwartete
Dateinamen:

- `bilder/hero.jpg` – allgemeines Hero-Bild (ohne Stellen-Parameter)
- `bilder/maschineneinrichter.jpg` – bei `?stelle=maschineneinrichter`
- `bilder/kurzdreher.jpg` – bei `?stelle=kurzdreher`

Querformat, mind. ~1600 px breit. Motiv rechts platzieren – links liegt die Textfläche.

Optional lässt sich ein echtes Beck-Logo hinterlegen (`bilder/beck-logo.svg` /
`bilder/beck-logo-weiss.svg`), es ersetzt dann automatisch den Text-Schriftzug.

## Stellen-Deeplinks für die Ad

Die Anzeige kann direkt auf eine Stelle verlinken; die Seite wählt sie vor und
startet beim Erfahrungs-Schritt:

- `…/?stelle=maschineneinrichter`
- `…/?stelle=kurzdreher`

## Screening (Vorfilterung)

Wer bei der Erfahrungsfrage „weder Ausbildung noch Erfahrung“ wählt, fällt aus dem
Prozess (kein Lead an Leadtable) und bekommt einen freundlichen Hinweis. So kommen
qualifizierte Bewerbungen bei euch an. Screen-out und Erfolg gelten nur für den
aktuellen Besuch – ein Seiten-Neuladen startet frisch.

## Bewerbungen (Leadtable)

Jede abgeschlossene Bewerbung wird per Webhook an Leadtable gesendet (Felder u. a.
`stelle`, `erfahrung`, `vorname`, `nachname`, `telefon`, `email`, `lebenslauf`,
`quelle`, `seite`). Der Webhook ist in `index.html` in der Variable `WEBHOOK_URL`
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
