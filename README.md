# ndu – Kurs-Plugin für Claude Code

Die Befehle des Kurses **„Programmieren mit AI“** (MSc Management by Innovation, NDU) als Claude-Code-Plugin. Kurs-Website: https://ndu.datamonkeys.ai

| Befehl | Wofür |
|---|---|
| `/ndu-idee` | Von der Idee zum Produkt-Brief (`docs/PRODUKT.md`) |
| `/ndu-brainstorm` | Funktionen sammeln, MVP schneiden, Issues schreiben – in `docs/BACKLOG.md` oder in Linear |
| `/ndu-linear` | Backlog nach Linear umstellen (Team, Projekt, Issues übertragen) |
| `/ndu-check` | Lint, Build, Secrets, Akzeptanzkriterien prüfen |
| `/ndu-review` | Strenge Prüfung mit frischem Blick (Secrets, Zugriffsregeln, Eingaben) |
| `/ndu-commit` | Änderungen sichern und pushen |
| `/ndu-explain` | Projekt oder Datei erklären lassen |
| `/ndu-beratung` | Zweitmeinung eines stärkeren Modells |
| `/ndu-neu` | Neues Produkt aus der Leihbar-Vorlage starten |

Alle Befehle startet nur ihr selbst – Claude ruft sie nicht von sich aus auf.

## Installieren

Das Setup-Skript des Kurses erledigt das. Von Hand im Terminal:

```bash
claude plugin marketplace add markesdo/ndu-plugin
claude plugin install ndu@ndu-kurs
```

Danach Claude neu starten. Die Befehle heißen wie bisher (`/ndu-check` …); ausgeschrieben auch `/ndu:ndu-check`.

**Wichtig:** Liegt im Projekt noch eine eigene Kopie in `.claude/commands/` (ältere Repos aus der Vorlage), gewinnt die Kopie. Damit die Plugin-Version gilt, die Kopien löschen.

## Aktualisieren

```bash
claude plugin marketplace update ndu-kurs
claude plugin update ndu@ndu-kurs
```

Danach Claude neu starten (oder `/reload-plugins`).

## Aufbau

- `.claude-plugin/marketplace.json` – Marketplace `ndu-kurs`
- `plugins/ndu/.claude-plugin/plugin.json` – Plugin `ndu` (ohne feste Version: jeder Commit ist ein Update)
- `plugins/ndu/skills/ndu-*/SKILL.md` – die Befehle

Die Regeln für Projekte mit Issues in Linear stehen nicht im Plugin, sondern im Projekt selbst (`docs/LINEAR.md`, eingebunden in `CLAUDE.md`).
