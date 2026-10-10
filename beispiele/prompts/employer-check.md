# /employer-check — Arbeitgeber-Due-Diligence

Aufruf: `/employer-check [Firma] (+ Rolle, Standort)`. Pflicht vor jeder
Bewerbung, bei Inbound-Kontakten parallel zum Erstgespräch.

## Ziel

Ehrliche, nichts erfindende Entscheidungsgrundlage über den **Arbeitgeber**.
Die Passung entscheidet die Eval. Vier Verdikte:

- **bestanden**
- **bestanden mit Vorbehalt**: offene Punkte werden Gesprächsfragen.
- **kritisch**: kein K.O., Empfehlung „nicht bewerben“, [Mensch] entscheidet.
  Nur aus Arbeitgebergründen, eines genügt, z. B.: wiederholte Verlustjahre,
  negatives Eigenkapital, Fortführungsvorbehalt, Eigentümerwechsel oder
  Restrukturierung mit unklarer Folge für die Rolle, Weiterempfehlung unter
  [Schwelle], gehäufte Führungs- oder Micromanagement-Muster in mehreren
  unabhängigen Reviews. Schwellen stehen in `red-flags.md`.
- **K.O.**: nur ein Treffer der Negativliste in `criteria.md`. Als „Persönliches
  K.O.“ markieren.

## Umfang

**Kurzcheck** für börsennotierte oder sehr große Firmen **ohne Krisensignal**
(Presse zu Restrukturierung, Entlassungen, Verkauf oder Gewinnwarnung in
12 Monaten; niedrige Weiterempfehlung). Pflicht: die drei Plattform-Checks,
Grundprofil, Kultur, Führung im Zielbereich, Red Flags, eine Presse-Suche plus
Gegenevidenz. Finanzen, Markt, Handelsregister-Recherche entfallen
(„n. a. (Kurzcheck)“). Krisensignal oder kein Konzern → voller Check.

## Lies vorher

`red-flags.md`, `criteria.md`, Stellendatei, Eval, Firmenliste. Ein noch
gültiger Report → nur Nachtrag.

## Prüfraster

Je Dimension mindestens 2 Quellen, sonst `[G]`.
1. Grundprofil: Eigentümer, Standorte, Geschäftsmodell, Größe
2. Finanzen: Ergebnis 3 Jahre, Finanzierung, Warnschwellen mit Fundstelle
3. Kultur und Reputation: Review-Themen, Auszeichnungen
4. Führung: Geschäftsführung, Wechsel, öffentliche Aussagen
5. Stellenmarkt: Wiederausschreibungen, Fluktuationsproxy
6. Markt (nur kleine Firmen oder unklares Geschäftsmodell)
7. Red Flags: Klagen, Presse, Review-Muster

**Immer:** kununu, Glassdoor, LinkedIn (Felder und Technik in den
Recherche-Hinweisen), Handelsregister-Auswertung, Presse mit Gegenevidenz
(„[Firma] Kritik / Probleme / Entlassungen“). **Review-Qualität** prüfen:
Häufung positiver Reviews, erbetene Bewertungen, Mehrfachbewertungen; bei
Manipulationshinweisen Konfidenz senken.

Captcha oder Login: nicht abbrechen, [Mensch] im Chat bitten, nie selbst lösen.
`[G]` nur, wenn auch mit Hilfe nichts kommt, mit Grund.

## Quellen und Konfidenz

- A `[H]`: Geschäftsberichte, Register, offizielle Mitteilungen
- B `[M]`: Qualitätsjournalismus, Auszeichnungen, Unternehmensseite
- C `[N]`: Bewertungsportale, Profilsignale; nie alleinige Basis einer Kernaussage
- Tabu: anonyme Foren, ungeprüfte Social-Media-Posts, SEO-Blogs

`[H]` ≥ 2 A · `[M]` 1 A + 1 B oder 2 B · `[N]` nur B/C · `[G]` nicht
triangulierbar. Jede Zahl mit Fußnote, Widersprüche benennen.

## Output

Zwei Dateien, keine Längenbegrenzung:

- `recherche-output/YYYY-MM-DD_employer-[firma-slug]_rohdaten.md`: ungekürzt,
  jede Zahl, jedes Zitat, jede Quelle mit URL und Abrufdatum, auch
  Negativergebnisse.
- `recherche-output/YYYY-MM-DD_employer-[firma-slug].md`: Bericht, auf Rohdaten
  rückführbar. Frontmatter zusätzlich:

```yaml
verdikt: bestanden | mit-vorbehalt | kritisch | ko
grund: [Kriterium oder Vorbehalt]
konfidenz: H | M | N | G
umfang: voll | kurzcheck
```

Gliederung: Entscheidungsdaten oben · Verdikt mit Ein-Satz-Bild · 5 wichtigste
Erkenntnisse · Befunde je Dimension · Red Flags und K.O.-Treffer · Grauzonen ·
Fragen fürs Erstgespräch · Ansprechpersonen (nur berufliche Angaben) ·
Checkliste ✅/[G]/n. a. · Quellenverzeichnis.

## Danach

- K.O. → Stelle auf 🔴, Stellendatei löschen, Eval-Nachtrag.
- bestanden / mit Vorbehalt und Empfehlung „bewerben“ → Bewerbungsordner anlegen,
  Stellendatei, Eval und Report hineinkopieren.
- kritisch → kein Ordner, Empfehlung auf [Mensch]-Entscheid.
- Firmenliste und Status nachziehen.
