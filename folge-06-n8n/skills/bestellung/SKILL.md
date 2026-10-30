---
name: bestellung
description: Gibt eine Kundenbestellung über n8n an die Rösterei weiter (Kunde, Sorte, Menge in kg).
---

# Bestellung weitergeben

1. Nimm aus der Nachricht den Kunden, die Sorte und die Menge in kg.
2. Führe mit exec genau diesen Befehl aus und setze die drei Werte ein:

   curl -s -X POST http://host.docker.internal:5678/webhook/bestellung -H "Content-Type: application/json" -d '{"kunde": "KUNDE", "sorte": "SORTE", "kg": MENGE}'

3. Antworte mit dem Text aus dem Feld antwort.
