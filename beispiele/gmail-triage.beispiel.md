# Postfach-Triage: Regelwerk (bereinigt)

> Anweisung für einen automatisierten, täglich laufenden Assistenten mit Zugriff
> auf das Postfach über einen Connector. Persönliche Absender, Label-IDs und
> private Themenlabels sind entfernt; Platzhalter in [eckigen Klammern].

## Grundprinzip

Kein automatisches Löschen. Klassifiziert wird ausschließlich über Labels.
Ein Löschvorschlag ist nur ein Vorschlag; gelöscht wird von Hand.

## Labels

**Funktionale Kernlabels, exklusiv: genau eines pro Thread**

| Label | Zweck für den Menschen | Verhalten des Assistenten |
|---|---|---|
| `@Action` | erfordert eigene Handlung | sparsam vergeben, nur mit Beleg im Thread, dass es noch offen ist |
| `@Waiting` | wartet auf Dritte | bei jedem Lauf aktiv prüfen, ob die erwartete Antwort da ist |
| `@Read` | Newsletter, Fachartikel | flüchtig, nach dem Lesen archivieren |
| `@Jobs` | Job-Alerts | hochvolumig, eigener Kanal statt @Read |
| `@Reference` | Dokumente, Verträge, Belege | dauerhafter Speicher |
| `@Check-Manually` | Assistent unsicher oder sicherheits-/finanzrelevant | Fallback statt Raten |
| `@Delete-Vorschlag` | Löschkandidat | Mensch entscheidet gesammelt |

**Metalabels**

| Label | Rolle |
|---|---|
| `@Korrigiert` | Lernsignal: wird **nur** gesetzt, wenn der Mensch eine echte Fehlklassifizierung korrigiert. Normales Abschließen eines Vorgangs ist keine Korrektur. |
| `@[Thema]` | optionale Themenlabels, die als alleiniges Label gelten (kein Kernlabel daneben) |

## Ablauf pro Lauf

1. `label:@Korrigiert` prüfen. Bei Treffern ableiten, welche Regel unten falsch
   oder unvollständig war, und das in der Zusammenfassung melden. Das Regelwerk
   selbst ändert nur der Mensch in einer gemeinsamen Sitzung.
2. Ungelabelte Threads der letzten 7–10 Tage suchen
   (`has:nouserlabels -in:sent -in:chat -in:draft after:[Datum]`) und labeln.
3. `label:@Waiting` aktiv durchsuchen, nicht nur den aktuellen Stapel. Erledigtes
   umlabeln.
4. Kurze Zusammenfassung: Anzahl je Label, neue @Action- und @Check-Manually-Fälle,
   gefundene Korrekturen.

**Auftragsgrenze:** Der automatische Lauf bearbeitet nur neue Mails. Der alte
Bestand wird nur in gemeinsamen Sitzungen auf ausdrückliche Anfrage bearbeitet,
auch wenn noch Kapazität übrig wäre.

## Klassifizierungsregeln

- **Konfidenz:** Unter etwa 85 % Sicherheit → `@Check-Manually` statt raten.
- **Zeitverfall:** Je älter eine Mail, desto unwahrscheinlicher ist sie noch offen.
  Ist unklar, ob erledigt → `@Check-Manually`. Zeigt der Thread selbst die
  Erledigung (z. B. eigene abschließende Antwort) → `@Reference`.
- **Bestellungen:** bestätigt, aber nicht geliefert → `@Waiting`, bis die
  Lieferung bestätigt ist.
- **Belege:** Rechnungen und Quittungen → immer `@Reference`, nie Löschvorschlag
  (Steuer, Garantie, Reklamation). Ausnahme nur für ausdrücklich benannte,
  steuerlich irrelevante Belege, z. B. [Supermarkt-Kassenbons].
- **Wiederkehrende Zyklen:** Für bekannte Abläufe mit mehreren getrennten Mails
  (z. B. [Abo: Bestellung → Versand → Zustellung]) alle zugehörigen Threads per
  Absendersuche finden und gemeinsam umlabeln, sobald der Zyklus abgeschlossen ist.
- **Bekannte Absendermuster:** Liste von Absendern mit Standardlabel, z. B.
  KI-Newsletter → `@Read`, Job-Portale → `@Jobs`, Sicherheitswarnungen und neue
  Logins → `@Action`, Versandbenachrichtigungen ohne Rechnung → `@Delete-Vorschlag`.
  [Die konkrete Absenderliste ist persönlich und hier entfernt.]
- **Gelesen/ungelesen** ist für die Einordnung irrelevant.
- **Labels immer auf Thread-Ebene** setzen.
