# /analyse — Tiefenanalyse eines Reports

Aufruf: `/analyse [Pfad zum Report] + Analysefokus`. Zweiter Schritt nach
/recherche, ebenso für Eval-Reports (Tiefenanalyse) und Employer-Reports
(Abwägung) nutzbar.

## Ziel

Aus Fakten Schlüsse und priorisierte Handlungsempfehlungen ziehen. Denken in
Hypothesen, Konsequenzen und Gegenargumenten. Keine neue Recherche außer bei
entscheidenden `[G]`-Lücken, und dann als solche gekennzeichnet.

## Regeln

- Datenbasis zuerst prüfen: Konfidenz gesamt des Inputs. `[N]` → Analyse mit
  Vorbehalt im Kopf. `[G]` → den Nutzer informieren, Nachrecherche empfehlen, erst dann weiter.
- Konfidenz-Labels des Inputs übernehmen: `[H]` trägt Kernaussagen, `[M]` wird
  als „wahrscheinlich" geführt, `[N]` nur als Stütze, `[G]` nur mit Vorbehalt.
  Nichts auffüllen, Lücken benennen.
- Widersprüche aus dem Input adressieren, nicht glätten.
- Jede Schlussfolgerung verweist auf einen Abschnitt des Inputs („vgl. §2.3").
- Bei Job-Themen das Profil aus `criteria.md`, `roles.md` und `profil.md` einbeziehen.

## Der Report enthält

1. Datenbasis-Bewertung (2–3 Sätze, kritische `[G]`-Zonen)
2. 3–5 Kernfragen, überschneidungsfrei und zusammen erschöpfend, wichtigste zuerst
3. Je Kernfrage 2–3 konkurrierende Hypothesen mit Evidenz, Konfidenz und
   Gegenevidenz (Tabelle)
4. Folgewirkungen der stärksten Hypothese: unmittelbar, mittelfristig, Wildcards
5. Red Teaming: mindestens 3 konkrete Angriffspunkte auf die Hauptschlussfolgerung
6. Synthese in drei Schichten: gesichert `[H]` / wahrscheinlich `[M]` / unbekannt `[G]`
7. 3–5 priorisierte Handlungsempfehlungen: Empfehlung, Begründung, Datenbasis
8. Executive Evaluation: 3–5 Sätze für Eilige

## Output

`analyse-output/YYYY-MM-DD_[thema-slug]-analyse.md`; bei Eval-Tiefenanalysen
`evaluation-output/..._tiefenanalyse.md`. Kopf: Thema, Datum, Input-Pfad,
Konfidenz Input und Analyse, Scope in 1–2 Sätzen. Terminal: Pfad + nächster Schritt.
