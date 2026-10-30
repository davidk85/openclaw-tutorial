# Folge 1: OpenClaw 2.0 installieren

Dein eigener KI-Agent mit Docker und Ollama, komplett lokal

▶ Video: folgt

## Was du lernst

- Was OpenClaw ist und was ein KI-Agent anders macht als ein Chatbot
- Warum lokale Modelle eine schlanke Konfiguration brauchen
- OpenClaw mit dem Begleit-Repo und docker compose starten
- Einen eigenen Zugangs-Token erzeugen und dich in der Control UI anmelden
- Die erste Nachricht an deinen Agenten

## Voraussetzungen

- Docker Desktop (Windows, Mac) oder Docker Engine mit Compose (Linux), siehe [n8n-Reihe, Folge 0](https://github.com/davidk85/n8n-tutorial/tree/main/folge-00-docker-start)
- [Ollama](https://ollama.com) mit dem Modell `ministral-3:3b` (`ollama pull ministral-3:3b`)
- Docker läuft (docker compose version zeigt eine Version an)

## Datenschutz

Mit Ollama bleiben deine Nachrichten und die Dateien des Agenten auf deinem Rechner. Wenn du später ein Cloud-Modell einträgst, gehen Nachrichten, gelesene Dateien und Ausgaben von Befehlen an diesen Anbieter. Keine Rechtsberatung.

## Zum Kopieren

**Begleit-Repo herunterladen**

```bash
git clone https://github.com/davidk85/openclaw-tutorial.git
```

**In den Ordner wechseln**

```bash
cd openclaw-tutorial
```

**Begleit-Repo auf GitHub**

```
https://github.com/davidk85/openclaw-tutorial
```

**Modell mit Ollama laden**

```bash
ollama pull ministral-3:3b
```

**Eigenen Token erzeugen (Mac und Linux)**

```
echo "OPENCLAW_GATEWAY_TOKEN=$(openssl rand -hex 24)" | tee .env
```

**OpenClaw starten**

```bash
docker compose up -d
```

**Control UI im Browser öffnen**

```
http://localhost:18789
```

**OpenClaw stoppen (die Daten bleiben erhalten)**

```bash
docker compose down
```

**Befehl aus dem Video**

```
ls workspace
```

## Quellen und weiterführende Seiten

- [OpenClaw auf GitHub](https://github.com/openclaw/openclaw)
- [OpenClaw: Installation mit Docker](https://docs.openclaw.ai/install/docker)
- [OpenClaw: Lokale Modelle](https://docs.openclaw.ai/gateway/local-models)
