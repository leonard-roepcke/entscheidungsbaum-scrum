# Entscheidungsbäume & Gini Impurity

Didaktisches Uni-Abschlussprojekt zum Thema Entscheidungsbäume und Gini Impurity im maschinellen Lernen.

**Live-Demo:** https://leonard-roepcke.github.io/entscheidungsbaum-scrum/

## Seiten

| Datei | Beschreibung |
|-------|--------------|
| [index.html](index.html) | Startseite mit Theorie-Überblick |
| [lernpfad.html](lernpfad.html) | **Empfohlener Einstieg** — interaktiver 10-Schritte-Kurs (0–100 %) |
| [gini-impurity.html](gini-impurity.html) | Interaktiver Gini-Rechner mit Rechenweg |
| [entscheidungsbaum.html](entscheidungsbaum.html) | Baum-Builder mit Split-Analyse und Selbsttest |

## Technische Anforderungen

- Jede Seite ist eine **eigenständige HTML-Datei** (HTML + CSS + JavaScript inline)
- **Keine externen Abhängigkeiten** — funktioniert offline per Doppelklick / `file://`
- Keine npm-Pakete, Frameworks oder Build-Tools nötig
- System-Schriftarten (kein Google Fonts CDN)

## Nutzung

1. Repository klonen oder ZIP herunterladen
2. Für Einsteiger: `lernpfad.html` im Browser öffnen
3. Für Vertiefung: `gini-impurity.html` und `entscheidungsbaum.html` ausprobieren

Der Lernpfad speichert den Fortschritt lokal im Browser (`localStorage`).

## Entscheidungsbaum-Seite

- URL-Parameter `?seed=42` für reproduzierbare Datensätze
- Split-Analyse-Tabelle zeigt Gini Impurity pro Merkmal (niedrigster gewichteter Gini = bester Split)
- Algorithmus: CART-ähnlich mit Gini Impurity, max. Tiefe 4, Mindest-Split-Größe 2
