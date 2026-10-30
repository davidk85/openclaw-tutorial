# OpenClaw-Tutorials von ToolVibes

Begleitmaterial zur Reihe über [OpenClaw](https://github.com/openclaw/openclaw) auf dem YouTube-Kanal **ToolVibes**:
eine fertige docker-compose.yml, eine Konfiguration für lokale Modelle mit Ollama, Skills und alle Befehle aus den
Videos zum Kopieren. OpenClaw ist ein KI-Agent, der nicht nur chattet, sondern Dateien bearbeitet, Befehle ausführt und
Aufgaben nach Zeitplan erledigt. Jede Folge hat einen eigenen Ordner mit Anleitung.

## Folgen

| Folge | Thema | Level |
|---|---|---|
| 1 | [OpenClaw 2.0 installieren](folge-01-installation/) | Einsteiger |
| 2 | [Dein erster OpenClaw-Agent](folge-02-erster-agent/) | Einsteiger |
| 3 | [Was darf dein OpenClaw-Agent?](folge-03-sicherheit/) | Einsteiger |
| 4 | [OpenClaw arbeitet nach Zeitplan](folge-04-automatisierungen/) | Fortgeschritten |
| 5 | [Gedächtnis und Skills in OpenClaw](folge-05-gedaechtnis-skills/) | Fortgeschritten |
| 6 | [OpenClaw und n8n verbinden](folge-06-n8n/) | Fortgeschritten |

## OpenClaw starten

Du brauchst Docker Desktop (Windows, Mac) oder Docker Engine mit Compose (Linux) und [Ollama](https://ollama.com) mit
dem Modell `ministral-3:3b`. Dann im Ordner dieses Repos einmal einen eigenen Zugangsschlüssel erzeugen und starten:

```bash
ollama pull ministral-3:3b
echo "OPENCLAW_GATEWAY_TOKEN=$(openssl rand -hex 24)" | tee .env
docker compose up -d
```

Danach http://localhost:18789 öffnen und den Schlüssel aus `.env` (alles nach dem Gleichheitszeichen) eingeben.
Unter Windows (PowerShell) legst du die Datei `.env` mit einem Editor an und trägst dort `OPENCLAW_GATEWAY_TOKEN=` und
eine lange, zufällige Zeichenfolge ein.

Die Videos nutzen OpenClaw 2026.10.9. Eine andere Version stellst du in `docker-compose.yml` ein.
Stoppen mit `docker compose down`. Die Dateien des Agenten liegen im Ordner `workspace`, Einstellungen und Chats im
Docker-Volume `openclaw-state`; beides bleibt erhalten (nur `docker compose down -v` löscht das Volume).

## Die Konfiguration

`openclaw.json` ist für kleine lokale Modelle eingestellt: Ollama auf deinem Rechner, ein schlanker
Systemprompt (`localModelLean`), das Werkzeugprofil `coding` und 16.000 Token Kontext. Ohne diese Einstellungen schickt
OpenClaw mit jeder Nachricht rund 17.000 Token Anweisungen, und ein kleines Modell braucht dafür auf einem normalen
Rechner mehrere Minuten. Regelmäßige Hintergrundläufe (Heartbeat) sind aus. Beim ersten Start kopiert `openclaw-init`
die Datei in das Volume; spätere Änderungen machst du in der Control UI unter Einstellungen.

## Hinweise

- OpenClaw ist nur auf deinem Rechner erreichbar (Port an 127.0.0.1 gebunden). Der Schlüssel in `.env` ist dein Login.
- Der Agent darf ab Werk Dateien schreiben und Befehle im Container ausführen. Wie du das einschränkst, zeigt Folge 3.
- Mit Ollama bleiben deine Chats und Dateien auf deinem Rechner. Mit einem Cloud-Modell gehen sie an den Anbieter.
- Kleine Modelle behaupten manchmal, etwas erledigt zu haben, ohne es getan zu haben. Prüfe Ergebnisse im Arbeitsbereich.
- Beispieldaten in den Videos sind erfunden, zum Beispiel die „Kaffeerösterei Morgenrot“.
