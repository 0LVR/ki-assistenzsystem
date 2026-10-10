# Job-Kriterien (Vorlage)

> Ebene L2: Datendatei. **Einzige Quelle** für Muss-Kriterien und Negativliste.
> Prompts und andere Dateien verweisen hierher. Bei Widerspruch gilt diese Datei.
> Alle Werte in [eckigen Klammern] sind Platzhalter.

## 1. Muss-Kriterien (K.O.)

> Fehlt eines davon → Absage, keine Ausnahme.

| # | Kriterium | Beschreibung |
|---|---|---|
| M1 | **Arbeitsort / Remote-Regel** | **Pendelregion** = [Stadt] und Umland bis ca. [1 h] einfache Fahrt (einzige Definition, gilt überall). In der Pendelregion: höchstens [x] Präsenztage pro Woche; im **Nahbereich** (ca. [Nahbereich 40 Min.]) sind mehr Präsenztage ein Einzelfall für den Menschen. Außerhalb der Pendelregion: [100 %] remote Pflicht. Maßstab ist die Präsenzpflicht im Büro, nicht Reisetätigkeit. |
| M1a | **Reise-Regel** | Projektbezogene, befristete Reisen zu Kunden verletzen M1 nicht. Dauerhafte Anwesenheit an einem festen Zweitstandort schon. |
| M2 | **KI-Einsatz möglich** | Die Rolle erlaubt oder fördert den Einsatz von KI-Werkzeugen. |
| M3 | **Kulturelle Passung** | [Werte, die der Arbeitgeber teilen muss] |
| M4 | **Gehalt ≥ [Untergrenze] € brutto/Jahr** | Nicht verhandelbar. Ohne Angabe wird nach fester Quellenreihenfolge geschätzt (siehe `prompts/evaluate-job.md`). |

## 2. Soll-Kriterien (Pluspunkte)

> Pluspunkte für Ranking und Anschreiben, **kein Ampelkriterium**. Unbekannt
> zählt nicht. Rollentyp und Priorität stehen nur in `roles.md`.

| # | Kriterium |
|---|---|
| S1 | Zielrolle mit Priorität 1–3 laut `roles.md` |
| S2 | Branche: [bevorzugte Branchen] |
| S3 | Weiterbildung strukturell möglich |
| S4 | Gehalt erreicht das Zielgehalt von [Obergrenze] |
| S5 | Unbefristeter Vertrag |

## 3. Nice-to-have

[4-Tage-Woche, Gestaltungsspielraum, kleines Team, …]

## 4. Negativliste

> Ein Treffer → Absage, unabhängig vom Rest.

- Verstoß gegen M1 oder M1a
- KI-Einsatz intern verboten oder blockiert
- [Eigentümer- oder Kulturmerkmale, die ausgeschlossen sind]
- Gehalt nachweislich unter M4
- [Rollenzuschnitte, die ausgeschlossen sind, z. B. Aufbauaufgabe plus volle Umsatzverantwortung]

## 5. Anwendung

Muss-Kriterien und Negativliste entscheiden (K.O. oder offen). Soll und
Nice-to-have sind Pluspunkte für das Ranking vergleichbarer Stellen. **Wie
bewertet wird (Reihenfolge, Ampel, Gehaltsschätzung, Empfehlung), steht nur in
`prompts/evaluate-job.md`**, nicht hier.
