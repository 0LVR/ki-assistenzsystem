# CLAUDE.md — Projektanker (Beispiel)

> Ebene L0 des Kontext-Frameworks. Diese Datei liest der Assistent bei jedem
> Sitzungsstart zuerst. Sie sagt, was das Projekt ist, welche Dateien Wahrheit
> sind und wie Prompts gebaut werden. Fakten stehen hier nicht.

## Was dieses Repo ist

Ein persönliches Assistenzsystem aus Prompts, Datendateien und Arbeitsergebnissen
für [Anwendungsbereiche, z. B. Jobsuche, Privatverkäufe, Postfach]. Kein Code.

## Ton

Direkt, knapp, mit Meinung. Keine Floskeln zur Eröffnung. Passt die Antwort in
einen Satz, reicht ein Satz. Schlechte Ideen werden benannt.

## Wahrheit (vor jeder Ausgabe lesen)

| Datei | Inhalt |
|---|---|
| `job-research/profil.md` | Werdegang, Stärken, Positionierung |
| `job-research/criteria.md` | Muss-Kriterien und Negativliste. **Einziger Ort dafür.** Alle anderen Dateien verweisen hierher. |
| `[modul]/data/[datei].md` | weitere Stammdaten je Modul |

Vorlagen mit `[Platzhaltern]` sind keine Wahrheit. Ihre Platzhalterwerte nie in
einer Ausgabe verwenden. Prompts, die auf einer leeren Vorlage beruhen, laufen
nicht, bis sie mit echten Daten gefüllt ist.

## Wie Prompts gebaut werden

Prompts definieren das Ziel, die harten Regeln und den Output-Vertrag (Datei,
Pfad, Länge, was danach nachgezogen wird). Sie schreiben das Denken nicht
Schritt für Schritt vor und wiederholen keine Fakten aus Datendateien. Eine
neue Regel kommt in die eine Datei, der sie gehört, nie in drei.

## Module

- `job-research/` — Stellen finden, bewerten, Arbeitgeber prüfen. Regeln:
  `job-research/CLAUDE.md`
- `job-application/` — Bewerbungsmappen, Tracker, Wiedervorlagen. Regeln:
  `job-application/CLAUDE.md`
- `[weiteres-modul]/` — [Zweck]

## Konventionen

- Sprache der Ausgaben: Deutsch, außer die Aufgabe verlangt anderes.
- Sagt ein Prompt „speichern unter [Pfad]“, wird gespeichert, nicht nur angezeigt.
- Alle Prompts sind als Slash-Commands registriert (`.claude/commands/`).
- Nach außen geht nichts ohne Freigabe: keine Mails, keine Uploads, keine Käufe.
