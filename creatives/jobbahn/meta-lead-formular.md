# Meta Instant Form (Lead-Formular) · Jobbahn → Beck · zum Reinkopieren
Stelle: Kurzdreher / Maschineneinrichter (m/w/d) · Seite/Absender: Jobbahn

> Hinweis zur KO-Logik: Meta-Lead-Formulare sortieren nicht automatisch aus.
> Die 4 Fragen unten liefern die Ja/Nein-Antworten – die eigentliche Absage/
> Qualifizierung macht ihr **downstream in Make/LeadTable** (nur Leads mit allen
> 4 = „Ja" weiterleiten/annehmen, Rest = „nicht qualifiziert").
> Alternativ als Anzeigenziel die **Landingpage mit echter KO-Logik** nutzen:
> https://saviold.github.io/beck-praezisionstechnik/jobbahn/

---

## 1) Name des Formulars (intern)
Beck – Kurzdreher/Maschineneinrichter – KO (Jobbahn)

## 2) Intro
**Formulartyp:** „Mehr Volumen" (mehr Leads) – oder „Höhere Absicht" für bessere Qualität (empfohlen).

**Begrüßung → Titel (max. 60):**
Kurzdreher / Maschineneinrichter (m/w/d) bei Beck

**Beschreibung → Variante A (Absatz):**
⚙️ Werde Teil von Beck Präzisionstechnik – seit 1952 Spezialist für Präzisionsdrehteile in Oberndorf a. N. Dich erwartet ein sicherer, unbefristeter Job mit fairer Bezahlung und modernster Technik. 🚀 Beantworte nur 4 kurze Fragen – ohne Anschreiben, ohne Lebenslauf – und wir melden uns persönlich bei dir.

**Beschreibung → Variante B (Liste):**
- Unbefristet & in Vollzeit
- Faire, pünktliche Bezahlung
- Moderner Maschinenpark (Sechsspindeltechnik)
- Familienbetrieb seit 1952
- In 60 Sek. bewerben – ohne Anschreiben

## 3) Fragen

**Kontaktinformationen (Meta-Standardfelder):**
- Vorname
- Nachname
- Telefonnummer
- E-Mail-Adresse

**Benutzerdefinierte Fragen – Typ „Multiple Choice", Antworten je: Ja / Nein**

1. Erfahrung an CNC-Dreh-/Mehrspindelautomaten – oder Ausbildung (z. B. Zerspanungsmechaniker)?
   • Ja  • Nein
2. Bereit, im Schichtbetrieb zu arbeiten?
   • Ja  • Nein
3. Standort Oberndorf a. N. erreichbar (Region oder umzugsbereit)?
   • Ja  • Nein
4. Gültige Arbeitserlaubnis für Deutschland?
   • Ja  • Nein

## 4) Datenschutzrichtlinie
**Link zur Datenschutzrichtlinie:** [eure Datenschutz-URL – z. B. https://laendle-digital.com/datenschutz/]

**Benutzerdefinierte Einwilligung (optionaler Haken) – Text:**
Mit dem Absenden willige ich ein, dass meine Angaben zur Prüfung meiner Bewerbung gespeichert, an den Arbeitgeber Beck Präzisionstechnik GmbH & Co. KG weitergeleitet und zur Kontaktaufnahme genutzt werden (Art. 6 Abs. 1 lit. a DSGVO). Keine Weitergabe an unbefugte Dritte, Widerruf jederzeit möglich.

## 5) Ende (Danke-Seite)
**Titel:**
Bewerbung eingegangen 🎉

**Beschreibung:**
Stark! Wir haben deine Angaben erhalten und melden uns persönlich bei dir. Schau auch kurz in dein Postfach.

**Button-Text:** Website ansehen
**Button-URL:** https://www.beck-praezisionstechnik.de/

---

## Optimierungen / Einstellungen
- Lead-Weiterleitung: an Make/LeadTable (Webhook/Integration) anbinden.
- Filter-Regel (Make/LeadTable): Lead nur annehmen/weiterleiten, wenn **alle 4 Fragen = „Ja"**. Sonst Status „nicht qualifiziert" (kein Weiterleiten an Beck).
