# mc-preise

Preisliste des Minecraft-Bedrock-Servers **19133** (QoL-Markt, Coins-Wirtschaft)
als statische Seite: **https://pib0t.github.io/mc-preise/**

- **617 Items** mit Kauf- und Verkaufspreis (Coins), Item-ID, Preisfaktor,
  Bestand und Handelszähler
- Suche, sortierbare Spalten, Filter, CSV-Export
- Einzelne HTML-Datei, keine Abhängigkeiten, funktioniert auch offline

## Preise

Kaufpreis = `max(1, round(Grundpreis · Faktor))`, Verkaufspreis =
`floor(Kauf / 2)` – der Server zahlt also höchstens die Hälfte des Kaufpreises an.
Ein Verkaufspreis von 0 bedeutet Überangebot: Der Markt nimmt das Item derzeit nicht.

Grundlage ist die Preisliste `2026-10-21-a0d5f792` aus dem Behavior-Pack des
Servers. Der Preisfaktor ist dynamisch (Angebot/Nachfrage); die Seite zeigt den
Stand des letzten Builds.

## Aktualisieren

Diese Seite wird nicht hier gepflegt, sondern aus dem Server-Repo erzeugt:

```bash
cd ~/docker/minecraft-bedrock-19133/qol-pack
./tools/publish-prices.sh --live   # Preise + Marktfaktoren neu bauen und pushen
```

Ohne `--live` entfällt der Serverabruf und es gilt überall Faktor 1,00.
