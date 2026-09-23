# /evaluate-job — Stellenbewertung

Aufruf: `/evaluate-job jobs/YYYY-MM-DD_[firma]_[titel].md`

## Ziel

Ampel (🟢 bewerben / 🟡 merken / 🔴 ablehnen) mit knapper Begründung als
Datei. Danach die Ablage nachziehen.

## Lies vorher

- `criteria.md` — Muss, Soll, Nice-to-have, Negativliste, Gewichtung
- `roles.md` — Zielrollen mit Priorität, Stärken, Lücken, Filterregeln
- die Stellenanzeige aus dem Aufruf

## Regeln

1. Muss-Kriterien M1–M4 zuerst. Ein ❌ → 🔴, der Rest entfällt. Standort- und
   Reiselogik stehen in criteria.md, nicht hier.
2. ⚠️ (unklar) bei M1, M2 oder M3 → höchstens 🟡, die Klärungsfrage wird zur
   offenen Frage. Fehlende Gehaltsangabe (M4 ⚠️) → 🟡. Vorher schätzen, wo
   es belegbar ist: Tarifangabe in der Anzeige (TVöD, TV-L, BG-AT, Chemie,
   IG Metall, TV-V …) → Tariftabelle nachschlagen und Jahresbrutto
   beziffern; sonst Entgeltatlas der Arbeitsagentur (Beruf + Region) als
   Median. Tarifwert ≥ Gehaltsuntergrenze aus criteria.md → M4 ✅ mit Quelle; Schätzung ohne Tarif bleibt ⚠️,
   aber mit Zahl.
3. Negativliste aus criteria.md: ein Treffer → 🔴.
4. Soll-Kriterien zählen (x/7). Rollen-Match: welche Rolle, hoch/mittel/niedrig,
   Seniorität realistisch? Welche Lücken aus roles.md fordert die Anzeige explizit?
5. ATS-Keywords: 5–10 Pflicht- und bis zu 5 Bonus-Keywords aus dem Anzeigentext,
   je mit ✅/⚠️/❌ gegen das Profil. Diese Liste ist Pflichtinput für
   den Faktencheck der Unterlagen.
6. Ampel nach Urteil, nicht nach Formel. 🟢 nur, wenn alle M ✅, Soll ≥ 4/7 und
   Rollen-Match mindestens mittel. Die Keyword-Quote zeigt den CV-Aufwand an,
   sie ist kein Ampelkriterium.
7. Nicht raten. Was die Anzeige nicht hergibt, ist ⚠️ mit einer konkreten Frage
   für die Klärungsmail (Vorlage „Klärungsmail“ im Bewerbungsmodul).

## Output

`evaluation-output/YYYY-MM-DD_[firma-slug]_[titel-slug]_eval.md`,
**höchstens 300 Wörter**:

- Ampel + ein Satz Begründung
- M1–M4 je eine Zeile: ✅/⚠️/❌ + Grund
- Negativliste: Treffer ja/nein
- Soll x/7, Rollen-Match, geforderte Lücken
- ATS-Keywords als Liste oder Tabelle
- Offene Fragen (nur bei 🟡)
- Nächster Schritt

Bei 🔴 durch K.O. reicht der Kopf: Ampel, verletztes Kriterium, ein Satz.

## Danach

- 🟢 → `/employer-check [Firma]` ist Pflicht vor der Übergabe an job-application.
- 🟡 → Datei nach `jobs/watchlist/` **verschieben** (nicht kopieren) und
  Frontmatter voranstellen:
  ```
  ---
  status: watchlist
  bewertet: YYYY-MM-DD
  wiedervorlage: YYYY-MM-DD        (+14 Tage)
  offene-frage: [konkrete Frage]
  eval: evaluation-output/[dateiname]_eval.md
  ---
  ```
- 🔴 → Datei aus `jobs/` löschen, der Eval-Report bleibt als Beleg.
- Immer: `status.md` (Historie-Tabelle, Funnel-Zähler, bei 🟡 Watchlist-Abschnitt).

Optional bei starken 🟢-Kandidaten: `/analyse` auf den Eval-Report (Werte-Fit,
implizite Risiken, Verhandlungsposition, Red Teaming) →
`evaluation-output/..._tiefenanalyse.md`.

## Input-Format für Stellen in `jobs/`

Volltext, nicht zusammenfassen (ATS-Keywords). Dateiname
`YYYY-MM-DD_[firma-slug]_[titel-slug].md`, Kleinschreibung, Datum = Funddatum.

```markdown
# [Jobtitel]

## Meta
- Unternehmen: / Standort: / Vertragsart: / Gehalt: („keine Angabe" erlaubt)
- Quelle: / Gefunden am: / URL:

## Aufgaben
## Anforderungen
## Über das Unternehmen
## Sonstiges
```
