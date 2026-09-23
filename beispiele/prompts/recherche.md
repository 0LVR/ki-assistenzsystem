# /recherche — Strukturierte Webrecherche

Aufruf: `/recherche [Thema, Zieltiefe, optional Zieldatei]`. Erster Schritt im
Zweischritt Recherche → /analyse. Der Report ist Rohmaterial für die Analyse,
deshalb strukturiert und mit Fußnoten.

## Ziel

Belastbare Fakten zu einem Thema, trianguliert, mit Konfidenz je Aussage, als
Datei. Keine Interpretation, keine Empfehlungen (das ist /analyse).

## Vorgehen

1. Lokalen Kontext lesen: Projekt-CLAUDE.md, bei Job-Themen `criteria.md` und
   `roles.md`, frühere Reports zum Thema in `recherche-output/` für den Delta-Vergleich
2. Scope festlegen: Thema, Tiefe (strategisch / operativ / wissenschaftlich),
   Zeitraum. Rückfrage nur bei echter Lücke im Kernauftrag, maximal zwei
3. Recherchieren entlang Wer / Was / Warum / Wie / Wann / Wo, mehrere
   unabhängige Suchen pro Kernfrage
4. Gegenevidenz aktiv suchen: mindestens eine Suche nach Kritik, Risiken, Gegenthesen

## Quellen und Konfidenz

- A: Primärquellen (Geschäftsberichte, offizielle Statistiken, Dokumentationen,
  Gesetze, Peer-Review, Whitepaper führender Institutionen)
- B: Qualitätsjournalismus (FAZ, Handelsblatt, FT, Reuters, Bloomberg,
  Economist, MIT Tech Review …)
- Tabu: SEO-Blogs, Wikipedia als alleinige Quelle, ungeprüfte Foren und Social Media

`[H]` ≥ 2 A-Quellen · `[M]` 1 A + 1 B oder 2 B ohne Widerspruch · `[N]` nur B
oder leichte Abweichungen · `[G]` nicht triangulierbar oder widersprüchlich.
Jede Zahl, jedes Datum, jede Kernaussage mit Fußnote `[x]`, Konfidenz inline
(`4,2 Mrd. € [H][1][2]`). Widersprüche stehen lassen: „Quelle [1] sagt A,
Quelle [2] sagt B." Nach 3 erfolglosen Suchen: `[G]` und weiter.

## Output

`recherche-output/YYYY-MM-DD_[thema-slug].md`:

- Kopf: Thema, Datum, Konfidenz gesamt, Quellenzahl
- Executive Summary: 3–5 Punkte mit Konfidenz
- Faktenlage nach den 6 W (Unterabschnitte, Fußnoten), Datenlisten als Tabellen
- Gegenevidenz und Widersprüche
- Offene Fragen für /analyse (Datenlücken, Spannungsfelder)
- Quellenverzeichnis `[n] Titel — URL`

Terminal: Pfad + Konfidenz gesamt.
