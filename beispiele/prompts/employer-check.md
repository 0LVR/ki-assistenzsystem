# /employer-check — Arbeitgeber-Due-Diligence

Aufruf: `/employer-check [Firma] (+ Rolle, Standort)`. Pflicht bei jeder
🟢-Stelle vor der Übergabe an job-application; bei Inbound-Kontakten parallel
zum ersten Gespräch.

## Ziel

Ehrliche Entscheidungsgrundlage: Stärken und Warnsignale gleich klar, nichts
erfunden. Ergebnis: bestanden oder K.O., plus Fragen fürs Erstgespräch.

## Lies vorher

`red-flags.md` vollständig (K.O.-Merkmale, Warnsignale Führung/Kultur), `criteria.md` (Kultur-Kriterium, Negativliste), Stellenanzeige und Eval-Report, falls vorhanden
(`jobs/`, `evaluation-output/`), Eintrag in `companies.md`.

## Prüfraster

Je Dimension mindestens 2 unabhängige Quellen, sonst `[G]`.

1. Grundprofil: Gründung, Eigentümer (börsennotiert / PE / Familie / Startup),
   Standorte, Geschäftsmodell, Mitarbeiterzahl und Trend
2. Finanzen: Umsatz/Ergebnis 3 Jahre, Finanzierung, Burn-Rate,
   Insolvenz-/Restrukturierungshistorie
3. Kultur/Reputation: wiederkehrende Review-Themen, Auszeichnungen — auf Basis
   der drei Pflichtchecks unten
4. Führung: Geschäftsführung (Hintergrund, Amtszeit), Wechsel der letzten
   2 Jahre, öffentliche Aussagen
5. Stellenmarkt: offene Stellen absolut/relativ, Wiederausschreibungen,
   Betriebszugehörigkeit (LinkedIn) als Fluktuationsproxy
6. Markt: Wettbewerber, Positionierung, Branchentrends, Kundenbewertungen
7. Red Flags: Klagen, Presse (Entlassungen, Skandale), Review-Muster
   („Hire and Fire", Micromanagement, Chaos), Führungswechsel plus
   Restrukturierung, Diskrepanz Selbstbild vs. Mitarbeiterfeedback

**Drei Plattform-Checks, immer, ohne Ausnahme** (Technik: `sources.md`):

- **kununu:** Score, Anzahl, Weiterempfehlung gesamt vs. 2 Jahre, Teil-Scores,
  Branchenvergleich, Gehälter-Tab, wiederkehrende Themen
- **Glassdoor:** Gesamt, Anzahl, Weiterempfehlung, CEO-Befürwortung,
  Geschäftsprognose, Standortverteilung, Vergütung; glassdoor.de und .com
- **LinkedIn:** Unternehmensseite (Mitarbeiterzahl, Wachstum, Standorte),
  Betriebszugehörigkeit im Zielbereich als Fluktuationsproxy, und
  **Ansprechpersonen**: Recruiter:in der Stelle, vermutliche Führungskraft
  (Leitung des Zielbereichs, z. B. Global IT / KI), 2–3 künftige
  Kolleg:innen. Nur berufliche Profilangaben (Rolle, Bereich, Seit wann,
  öffentliche Beiträge zum Thema), keine Privatdaten.

Dazu immer:

- **North Data** (northdata.de): Geschäftsführung und Wechsel, Gesellschafter,
  Beteiligungen, Insolvenz-/Registerereignisse, Bilanzkennzahlen — Pflichtbeleg
  für Dimension 1, 2, 4 und die Prüfung der Eigentümer- und Entscheiderstruktur
- **Indeed-Unternehmensdaten** (MCP `get_company_data`): dritte
  Bewertungsquelle neben kununu und Glassdoor
- Bei nicht börsennotierten Firmen: **Bundesanzeiger / Unternehmensregister**
  (Jahresabschlüsse)

Captcha oder Login: nicht abbrechen, sondern den Nutzer im Chat um Unterstützung
bitten (Tab offen lassen, Seite und Schritt nennen) und danach weiterlesen —
ein vollständiges Ergebnis hat Vorrang vor Tempo. Captchas und Passwörter
nie selbst lösen oder eingeben. `[G]` nur, wenn die Quelle auch mit Hilfe des
Nutzers nichts liefert (kein Profil, Paywall) — mit Grund, nie stillschweigend.

Pflicht dazu: Abgleich mit den persönlichen K.O.-Kriterien (red-flags.md, Negativliste in criteria.md). Treffer explizit als „Persönliches K.O." markieren.
Gegenevidenz: mindestens eine Suche nach „[Firma] Kritik / Probleme /
Entlassungen" und nach Gegenbelegen zu gefundenen Red Flags.

## Quellen und Konfidenz

- A `[H]`: Geschäftsberichte, Bundesanzeiger, Handelsregister, offizielle
  Pressemitteilungen
- B `[M]`: Qualitätsjournalismus (Handelsblatt, FAZ, FT, Reuters …),
  Arbeitgeber-Auszeichnungen, LinkedIn-Unternehmensseite
- C `[N]`: Kununu, Glassdoor, LinkedIn-Profilsignale, Trustpilot/G2. Erlaubt für
  Kultur und Fluktuation, immer mit Plattform-Vorbehalt, nie alleinige Basis
  einer Kernaussage
- Tabu: anonyme Foren, ungeprüfte Social-Media-Posts, SEO-Blogs

`[H]` ≥ 2 A-Quellen · `[M]` 1 A + 1 B oder 2 B · `[N]` nur B/C · `[G]` nicht
triangulierbar oder widersprüchlich. Jede Zahl mit Fußnote `[x]`. Widersprüche
benennen, nicht glätten. Nach 3 erfolglosen Suchen: `[G]` und weiter.

## Output

Zwei Dateien, keine Längenbegrenzung:

- `recherche-output/YYYY-MM-DD_employer-[firma-slug]_rohdaten.md` —
  **ungekürzt**: jede gefundene Zahl, jedes Review-Zitat, jede Quelle mit URL
  und Abrufdatum, auch Negativergebnisse („3 Suchen ohne Treffer: …"), je
  Plattform ein eigener Abschnitt, Ansprechpersonen als Tabelle. Nichts
  zusammenfassen — diese Datei ist die Beweisgrundlage.
- `recherche-output/YYYY-MM-DD_employer-[firma-slug].md` — der Bericht, aus
  den Rohdaten abgeleitet, jede Aussage auf die Rohdaten rückführbar:

1. Ergebnis: bestanden / K.O. (welches) + Gesamtbild in einem Satz + Konfidenz
2. Die 5 wichtigsten Erkenntnisse mit Konfidenz
3. Befunde je Dimension 1–7, knapp, mit Fußnoten
4. Red Flags und persönliche K.O.-Treffer; sonst: „keine gefunden, Abwesenheit
   von Evidenz ist keine Evidenz der Abwesenheit"
5. Grauzonen und Widersprüche
6. Fragen fürs Erstgespräch (aus den Grauzonen)
7. Ansprechpersonen: wer für Rückfragen, wer als Gesprächspartner:in
   (Recruiting, Fachbereich, Führung) — mit LinkedIn-URL
8. Checkliste: kununu ✅/[G] · Glassdoor ✅/[G] · LinkedIn ✅/[G] ·
   North Data ✅/[G] · Indeed ✅/[G] · Bundesanzeiger ✅/[G]/n. a. ·
   Dimensionen 1–7 ✅/[G] · Gegenevidenz-Suche ✅
9. Quellenverzeichnis

## Danach

- K.O. → Stelle in `status.md` auf 🔴 zurückstufen, Eval-Report um Nachtrag ergänzen
- Bestanden → Übergabe an job-application: Ordner
  `../job-application/applications/YYYY-MM-DD_[firma-slug]/` anlegen,
  `job-posting.md`, `eval.md`, `employer-check.md` und
  `employer-check_rohdaten.md` hineinkopieren, `status.md`
- `companies.md`: Status 🔍 Geprüft + Einzeiler
- Bei komplexer Abwägung optional `/analyse` auf den Report
