# Pricing-Philosophie — Preisbänder statt Punktschätzungen

Warum unsere Preise als Bänder kommuniziert werden und nicht als feste Einzel­zahl pro Anfrage.

## Drei Prinzipien

### 1. Preise sind transparent, bevor das Gespräch beginnt
Unser AI-Readiness-Check ([block-builder.de/de/estimator](https://block-builder.de/de/estimator)) liefert ein Preisband **vor** dem ersten Call. Wer einen Workshop bucht, weiß vorher, was das kostet. Wir verhandeln keine Wunschbudgets und keine Mondpreise.

### 2. Festpreise wo möglich, T&M wo ehrlich
| Format | Modell | Warum |
|---|---|---|
| Workshop, Assessment, Pilot | **Festpreis** | Scope ist abgrenzbar, Risiko liegt bei uns |
| Implementierung in Production | **T&M oder Festpreis nach Scoping** | Scope wächst während Bauphase mit, ehrlicher als ein Fantasie-Festpreis |
| Ongoing Advisory | **Monatlicher Festpreis** | Verlässlichkeit für beide Seiten |

Wir scheuen uns nicht vor Festpreisen — wir nehmen sie aber nur, wenn der Scope wirklich klar ist. "Festpreis um jeden Preis" produziert entweder schlechte Liefer­qualität oder bittere Nachverhandlungen.

### 3. Preise reflektieren Senior-Stundensätze
Senior-only-Delivery kostet mehr pro Stunde als Junior-Bodyleasing. Sie liefert dafür weniger Stunden für dasselbe Ergebnis. Über die Gesamt­strecke ist das oft günstiger — aber nur, wenn der Kunde die Logik mitträgt.

## Was wir nicht machen

### Keine "auf Anfrage"-Preise für KMU-Standard­leistungen
Wenn ein 3-stündiger Solo-AI-Workshop angeboten wird, steht der Preis (480 EUR netto) auf der Website. Punkt.

### Keine Volumen-Rabatte als Sales-Hebel
Wir geben keine "Erstkunden-Rabatte", die ein verkapptes Underselling sind. Wenn ein Preis falsch wäre, korrigieren wir den Preis — nicht einmalig die Rechnung.

### Keine Lock-in-Verträge
Ongoing Advisory ist monatlich kündbar. Implementations­projekte haben sauber definierte Meilensteine — und Kunden können nach jedem Meilenstein aussteigen.

## Was Preise treibt

| Faktor | Effekt |
|---|---|
| **Datenresidenz On-Premise** | Setup-Aufwand höher (Hardware, GPU-Konfiguration) |
| **Integration in bestehende Legacy-Systeme** | Integrations­aufwand oft 30–50% des Projekt­budgets |
| **Compliance-Anforderungen (Hochrisiko EU AI Act, regulierte Branchen)** | Doku- und Review-Aufwand substanziell |
| **Modell-Wahl (Self-Hosted vs API)** | Self-Hosted: Initial höher, laufend günstiger |
| **Datenqualität** | Schlechte Daten = viel ETL-/Cleaning-Arbeit vor dem ersten Modell-Call |

## Konkrete Preis­anker (öffentlich kommuniziert)

| Format | Preis |
|---|---|
| Solo-AI-Workshop (3h) | 480 EUR netto |
| AI-Discovery-Workshop (1–2 Tage) | ab 1.500 EUR |
| AI-Readiness-Assessment (1–2 Wochen) | ab 3.500 EUR |
| AI-Pilot (Working Prototype, 8 Wochen) | ab 18.000 EUR |
| On-Premise-Hardware (Einstieg) | ~15.000 EUR einmalig |
| On-Premise laufend | ~300 EUR/Monat |
| Cloud-Hosted-Instanz | ab 499 EUR/Monat |

Alles netto, zzgl. USt.

**Verwandt:**
- Engagement-Modelle: `pricing/engagement-models.md`
- Readiness-Check: `pricing/readiness-check.md`
