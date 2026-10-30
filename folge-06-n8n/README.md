# Folge 6: OpenClaw und n8n verbinden

Der Agent versteht die Bestellung, n8n erledigt den Rest

▶ Video: folgt

## Was du lernst

- Warum Agent und Workflow zusammen stark sind
- Den n8n-Workflow mit Webhook und Mail importieren und veröffentlichen
- Einen Skill schreiben, der einen Webhook aufruft
- Den Aufruf im Modus Geschützt vorher prüfen und erlauben
- Das Ergebnis im Postfach kontrollieren

## Voraussetzungen

- Ein laufendes OpenClaw: [OpenClaw starten](../README.md#openclaw-starten)
- OpenClaw mit Ollama (Folge 1), Skills (Folge 5)
- n8n mit Docker und Mailpit, zum Beispiel aus dem Begleit-Repo der n8n-Reihe (https://github.com/davidk85/n8n-tutorial)
- Ein SMTP-Zugang in n8n: zum Testen Mailpit (Host mailpit, Port 1025, SSL aus, Postfach unter http://localhost:8025)

## Datenschutz

Kundennamen und Bestellungen sind oft personenbezogene Daten. Hier bleiben sie auf deinem Rechner: lokales Modell, lokales n8n, Test-Postfach. Mit einem Cloud-Modell gehen die Nachrichten an den Anbieter. Mehr dazu in Folge 12 der n8n-Reihe. Keine Rechtsberatung.

## Dateien

- [`skills/bestellung/SKILL.md`](skills/bestellung/SKILL.md) – Der Skill „bestellung“ aus dem Video
- [`bestellung.json`](bestellung.json) – n8n-Workflow „Bestellung von OpenClaw“ (Webhook, Mail, Antwort)

## Workflow importieren

1. JSON-Datei öffnen und den gesamten Inhalt kopieren (auf GitHub: Button „Copy raw file“).
2. In n8n einen neuen, leeren Workflow öffnen und mit Strg+V (Mac: Cmd+V) einfügen.
3. Nodes mit Zugangsdaten öffnen und deine eigenen auswählen – die Dateien enthalten keine.
4. Speichern und oben rechts mit „Publish“ veröffentlichen, damit die Production-URLs funktionieren.

## Zum Kopieren

**Befehl aus dem Video**

```
cat folge-06-n8n/skills/bestellung/SKILL.md
```

**Skill in den Arbeitsbereich kopieren**

```
cp -r folge-06-n8n/skills workspace/
```

## Quellen und weiterführende Seiten

- [OpenClaw: Eigene Skills erstellen](https://docs.openclaw.ai/tools/creating-skills)
- [n8n: Webhook-Node](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.webhook/)
