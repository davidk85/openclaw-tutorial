# Folge 5: Gedächtnis und Skills in OpenClaw

Dein Agent merkt sich Fakten und lernt eine neue Aufgabe

▶ Video: folgt

## Was du lernst

- Wie OpenClaw sich Dinge merkt (MEMORY.md und Tagesnotizen)
- Den Agenten ausdrücklich etwas in MEMORY.md schreiben lassen
- In einem neuen Chat prüfen, was der Agent weiß
- Einen eigenen Skill als Ordner mit SKILL.md anlegen
- Einen Skill per Slash-Befehl aufrufen

## Voraussetzungen

- Ein laufendes OpenClaw: [OpenClaw starten](../README.md#openclaw-starten)
- OpenClaw mit Ollama (Folge 1), Agent mit Profil (Folge 2)

## Datenschutz

MEMORY.md geht bei jedem neuen Chat an das Modell. Mit Ollama bleibt das auf deinem Rechner, mit einem Cloud-Modell nicht: dann keine Kundendaten oder Passwörter hineinschreiben lassen. Keine Rechtsberatung.

## Dateien

- [`skills/angebot/SKILL.md`](skills/angebot/SKILL.md) – Der Skill „angebot“ aus dem Video
- [`preise.md`](preise.md) – Erfundene Preisliste der Kaffeerösterei Morgenrot

## Zum Kopieren

**Befehl aus dem Video**

```
cat folge-05-gedaechtnis-skills/skills/angebot/SKILL.md
```

**Skill in den Arbeitsbereich kopieren**

```
cp -r folge-05-gedaechtnis-skills/skills workspace/
```

**Preisliste in den Arbeitsbereich kopieren**

```
cp folge-05-gedaechtnis-skills/preise.md workspace/
```

## Quellen und weiterführende Seiten

- [OpenClaw: Gedächtnis](https://docs.openclaw.ai/concepts/memory)
- [OpenClaw: Eigene Skills erstellen](https://docs.openclaw.ai/tools/creating-skills)
