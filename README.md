# Entscheidungsbäume & Gini Impurity

Didaktisches Uni-Abschlussprojekt zum Thema **Entscheidungsbäume** und **Gini Impurity** im maschinellen Lernen. Vier interaktive HTML-Seiten erklären die Konzepte Schritt für Schritt — mit Übungen, Rechnern und einem Baum-Builder zum Selbstausprobieren.

**Live-Demo:** [leonard-roepcke.github.io/entscheidungsbaum-scrum](https://leonard-roepcke.github.io/entscheidungsbaum-scrum/)

## Für wen ist das?

- Studierende und Einsteiger im maschinellen Lernen
- Lehrkräfte, die ein offline-fähiges Unterrichtsmaterial suchen
- Alle, die Entscheidungsbäume und Gini Impurity praktisch verstehen wollen — ohne Installation oder Frameworks

## Schnellstart

```bash
git clone https://github.com/leonard-roepcke/entscheidungsbaum-scrum.git
cd entscheidungsbaum-scrum
```

Dann im Browser öffnen:

1. **Einsteiger:** [`lernpfad.html`](lernpfad.html) — geführter 10-Schritte-Kurs (0–100 %)
2. **Vertiefung:** [`gini-impurity.html`](gini-impurity.html) und [`entscheidungsbaum.html`](entscheidungsbaum.html)
3. **Theorie-Überblick:** [`index.html`](index.html)

Alternativ: ZIP herunterladen und eine beliebige HTML-Datei per Doppelklick öffnen. Alles funktioniert offline über `file://`.

## Seiten im Überblick

| Seite | Datei | Inhalt |
|-------|-------|--------|
| Startseite | [`index.html`](index.html) | Theorie-Überblick zu Gini Impurity und Entscheidungsbäumen, Formeln, Erklärvideo |
| **Lernpfad** | [`lernpfad.html`](lernpfad.html) | **Empfohlener Einstieg** — 10 interaktive Schritte mit Aufgaben und Fortschrittsanzeige |
| Gini-Rechner | [`gini-impurity.html`](gini-impurity.html) | Live-Rechner mit vollständigem Rechenweg und einstellbaren Klassenverteilungen |
| Baum-Builder | [`entscheidungsbaum.html`](entscheidungsbaum.html) | Interaktiver Baum zum Selbstbauen, Split-Analyse und automatische Gini-Lösung |

Alle Seiten sind über eine gemeinsame Navigation verknüpft.

## Lernpfad (10 Schritte)

Jeder Schritt erklärt ein Konzept und enthält eine kleine Aufgabe. Erst nach dem Lösen geht es weiter. Der Fortschritt wird im Browser gespeichert (`localStorage`, Schlüssel `lernpfad-fortschritt-v2`).

| # | Thema | Was du lernst |
|---|-------|---------------|
| 1 | Klassifikation | Was Klassifikation ist und wofür sie gebraucht wird |
| 2 | Entscheidungsbaum | Die Grundidee anhand eines Alltagsbeispiels (Regenschirm?) |
| 3 | Baum-Teile | Wurzel, Knoten, Ast und Blatt zuordnen |
| 4 | Unreinheit | Warum man ein Maß für „Gemischtheit" in Daten braucht |
| 5 | Gini-Formel | Die Formel `Gini = 1 − Σ (pᵢ)²` Schritt für Schritt |
| 6 | Gini berechnen | Gini-Werte selbst ausrechnen |
| 7 | Bester Split | Den Split mit der niedrigsten gewichteten Gini-Unreinheit erkennen |
| 8 | Baum wächst | Wie ein Baum rekursiv aus den besten Splits entsteht |
| 9 | Wissens-Check | Abschluss-Quiz zu den gelernten Konzepten |
| 10 | Abschluss | Zusammenfassung mit Links zu Rechner und Baum-Builder |

## Baum-Builder im Detail

Auf [`entscheidungsbaum.html`](entscheidungsbaum.html) baust du einen Entscheidungsbaum anhand eines zufälligen Trainingsdatensatzes:

- **Datensatz:** 10–12 Beispiele mit Merkmalen Farbe, Form und Buchstabe; Zielvariable „Happy / Not Happy"
- **Interaktion:** Knoten selbst als Split oder Blatt setzen, dann mit „Prüfen" validieren
- **Nach dem Prüfen:** Split-Analyse-Tabelle (Gini Impurity pro Merkmal und Knoten) und die berechnete Gini-optimale Lösung
- **Algorithmus:** CART-ähnlich mit Gini Impurity, maximale Tiefe 4, Mindest-Split-Größe 2

### URL-Parameter

| Parameter | Beispiel | Wirkung |
|-----------|----------|---------|
| `seed` | `?seed=42` | Reproduzierbarer Datensatz (gleicher Seed → gleiche Daten) |

Ohne `seed` wird bei jedem Laden ein neuer Zufallssatz erzeugt. Mit dem Button „Neue Daten" wird der Seed inkrementiert.

## Gini-Rechner im Detail

Auf [`gini-impurity.html`](gini-impurity.html) kannst du Klassenverteilungen per Slider einstellen und siehst:

- den berechneten Gini-Wert in Echtzeit
- den vollständigen Rechenweg mit Zwischenschritten
- visuelle Einordnung (rein vs. gemischt)

## Technische Eigenschaften

- **Eigenständige HTML-Dateien** — HTML, CSS und JavaScript jeweils inline in einer Datei
- **Keine externen Abhängigkeiten** — kein npm, kein Build-Schritt, kein Framework
- **Offline-fähig** — funktioniert per Doppelklick oder `file://`
- **System-Schriftarten** — kein Google Fonts oder anderes CDN
- **Responsives Layout** — nutzbar auf Desktop und Mobilgeräten
- **Barrierefreiheit** — semantisches HTML, ARIA-Labels und Tastaturbedienung wo sinnvoll

## Projektstruktur

```
entscheidungsbaum-scrum/
├── index.html              # Startseite mit Theorie
├── lernpfad.html           # Interaktiver 10-Schritte-Kurs
├── gini-impurity.html      # Gini-Rechner mit Rechenweg
├── entscheidungsbaum.html  # Baum-Builder mit Split-Analyse
├── README.md
└── promts/                 # Entwicklungs-Prompts (siehe unten)
```

## Prompts (`promts/`)

Im Ordner `promts/` liegen die KI-Prompts, mit denen die Seiten iterativ entwickelt wurden. Sie dienen der Nachvollziehbarkeit und als Vorlage für ähnliche didaktische Projekte — Endnutzer der Lernseiten brauchen sie nicht.

| Datei / Ordner | Inhalt |
|----------------|--------|
| [`promtguide.txt`](promts/promtguide.txt) | Allgemeine Vorgaben (Technik, Didaktik, Design) für alle Prompts |
| [`startpage_promt/`](promts/startpage_promt/) | Prompts für die Startseite (`index.html`) |
| [`lernpfad_promt/`](promts/lernpfad_promt/) | Prompts für den interaktiven Lernpfad |
| [`prompt-gini-impurity1.txt`](promts/prompt-gini-impurity1.txt), [`prompt-gini-impurity2.txt`](promts/prompt-gini-impurity2.txt) | Prompts für den Gini-Rechner |
| [`entscheidungsbaum_promt/`](promts/entscheidungsbaum_promt/) | Prompts für den Baum-Builder (7 Iterationen) |

## Deployment (GitHub Pages)

Das Projekt ist als statische Seite auf GitHub Pages gehostet. Für ein eigenes Deployment reicht es, die HTML-Dateien in ein Repository zu pushen und GitHub Pages auf den `main`-Branch zu aktivieren — ohne Build-Konfiguration.

## Lizenz

Keine Lizenz angegeben. Bei Weiterverwendung bitte mit dem Autor klären.
