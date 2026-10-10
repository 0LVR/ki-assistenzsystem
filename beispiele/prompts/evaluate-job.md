# /evaluate-job — Stellenbewertung

Aufruf: `/evaluate-job jobs/YYYY-MM-DD_[firma]_[titel].md`

## Ziel

Ampel und Empfehlung mit knapper Begründung als Datei, dazu die ATS-Keywords
für das CV-Tailoring. Danach die Ablage nachziehen. Die Entscheidung über
Bewerbung und Versand trifft [Mensch].

## Lies vorher

`criteria.md` (Muss, Pendelregion, Negativliste, Soll), `roles.md` (Zielrollen,
Priorität, Lücken, Artefakt-Bedingungen), die Master-Datei mit Belegen (was ist
nachweisbar), `formate.md` (Stellendatei, Frontmatter), die Stellenanzeige.

## Regeln

1. **Liveness zuerst.** Anzeige offline → nicht bewerten, Datei zu den
   vergebenen Stellen. Ältere Eval derselben Firma und Rolle = Neuausschreibung:
   alte Eval verlinken, nur Änderungen bewerten.
2. **Muss M1–M4 zuerst.** Ein ❌ → 🔴. ⚠️ bei M1–M3 → höchstens 🟡, die
   Klärungsfrage wird offene Frage. Pendelregion-Definition nur in `criteria.md`.
3. **M4 immer mit Zahl und Quelle.** Erste belastbare Quelle zählt:
   Anzeige → Tarif → Entgeltatlas → Gehaltsreport → Firmenwerte. Nie Bänder aus
   `roles.md`. Anzeige oder Tarif ≥ [Untergrenze] → ✅; eindeutig darunter → ❌.
   Sonst Entgeltatlas-Median ≥ [Untergrenze] → „✅ geschätzt“, darunter ⚠️ mit Zahl.
4. **K.O. auch bei** Negativlisten-Treffer und geforderter Personalverantwortung,
   wenn `roles.md` sie ausschließt.
5. **Rolle und Match** laut `roles.md`. Soll-Kriterien sind Pluspunkte
   (unbekannt zählt nicht), kein Ampelkriterium.
6. **Harte Pflichtlücke** = als Muss formuliert und in der Master-Datei nicht
   belegt. „Oder vergleichbar“ macht eine Anforderung weich.
7. **Ampel nach Urteil:**
   - 🟢 = M1–M3 ✅, M4 ✅ (auch geschätzt), keine Negativliste, Match ≥ mittel,
     keine harte Pflichtlücke.
   - 🟡 = kein K.O., aber etwas offen.
   - 🔴 = K.O. oder falsches Berufsbild oder aussichtslose Kernanforderung.
     Schließt ein geplantes Artefakt die Lücke → 🟡 „geparkt“.
8. **Empfehlung** (außer 🔴): 🟢 → bewerben. 🟡 → bewerben · [Mensch]-Entscheid ·
   geparkt (mit Bedingung) · beobachten.
9. **Tragende Annahme:** ein Satz, welche Annahme das Urteil trägt und am
   ehesten kippt. Pflichtfeld, später gegen den Ausgang geprüft.
10. **ATS-Keywords:** 5–10 Pflicht, bis 5 Bonus, je ✅/⚠️/❌ gegen die
    Master-Datei.
11. **Nicht raten.** Unklares ist ⚠️ mit konkreter Frage. Offene Fragen gehen
    standardmäßig ins Anschreiben; eine Klärungsmail ist die Ausnahme.

## Output

`evaluation-output/YYYY-MM-DD_[firma-slug]_[titel-slug]_eval.md`: Frontmatter,
darunter höchstens 350 Wörter: Ampel + Empfehlung + ein Satz · M1–M4 je eine
Zeile (M4 mit Zahl und Quelle) · Negativliste · Rolle, Match, Soll-Pluspunkte,
Lücken · ATS-Keywords · offene Fragen (🟡) · nächster Schritt. Bei 🔴 durch
K.O.: Frontmatter und Kopf.

```yaml
---
ampel: 🟢 | 🟡 | 🔴
empfehlung: bewerben | [Mensch]-entscheid | geparkt | beobachten | —
m1: ✅ | ⚠️ | ❌
m2: ✅ | ⚠️ | ❌
m3: ✅ | ⚠️ | ❌
m4: ✅ | ✅ geschätzt | ⚠️ | ❌
m4-zahl: "[Kennzahl + Quelle]"
rolle: [Zielrolle] | —
match: hoch | mittel | niedrig
harte-luecke: [kurz] | keine
soll: [x/Anzahl]
tragende-annahme: "[ein Satz]"
bewertet: YYYY-MM-DD
---
```

## Danach

- 🟢 → `/employer-check` ist Pflicht vor der Übergabe an die Bewerbung.
- 🟡 → Datei nach `jobs/watchlist/` verschieben, Wiedervorlage-Datum setzen.
- 🔴 → Stellendatei löschen, die Eval bleibt als Beleg.
- Immer: Status-Datei und Funnel-Zähler nachziehen.

Optional: ein kleiner Regressionstest mit festen Beispielstellen prüft, ob
Prompt-Änderungen die Ampeln verschieben.
