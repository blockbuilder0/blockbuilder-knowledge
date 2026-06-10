# EU AI Act in unseren Projekten

Der EU AI Act ist seit 2024 in Kraft. Pflichten greifen gestuft — nach dem Digital Omnibus (Mai 2026) bis voraussichtlich Ende 2027 (Annex III) bzw. August 2028 (Annex I); Verbote, KI-Kompetenz und GPAI-Pflichten gelten bereits seit 2025. Details: compliance/eu-ai-act-leitfaden.md Wir berücksichtigen ihn in jedem Projekt, in dem KI eingesetzt wird — nicht als Audit-Pflicht­übung, sondern als Architektur-Filter.

## Vorgehen pro Projekt

### 1. Risiko-Klassifikation
Zu Projektbeginn klären wir die Einstufung:

- **Unannehmbar (verboten)**: Social Scoring, Manipulation, biometrische Echtzeit-Überwachung im öffentlichen Raum. Solche Projekte nehmen wir nicht an.
- **Hochrisiko**: HR/Recruiting, Bildung, kritische Infrastruktur, medizinische Geräte u.a. (Anhang III des AI Act). Hier ist die Pflichtenlage substanziell — Risiko­management­system, Datenqualitäts­anforderungen, technische Doku, menschliche Aufsicht, Konformitäts­bewertung. Wir nehmen solche Projekte nur mit klar abgesteckten Compliance-Pflichten und in Kooperation mit Fach­anwält:innen an.
- **Begrenztes Risiko**: Chatbots, generative Systeme, Deepfake-fähige Systeme. Transparenz­pflichten ("Sie sprechen mit einer KI", "Dieser Inhalt wurde KI-generiert"). Standard­fall für viele unserer Projekte.
- **Minimales Risiko**: Spam-Filter, Empfehlungssysteme. Keine spezifischen AI-Act-Pflichten.

### 2. Technische Vorkehrungen je Risiko­klasse

| Anforderung | Hochrisiko | Begrenzt | Minimal |
|---|---|---|---|
| Risiko­management­system | Pflicht | empfohlen | optional |
| Daten-Governance / Bias-Check | Pflicht | empfohlen | optional |
| Technische Doku | Pflicht | empfohlen | optional |
| Logging / Audit-Trail | Pflicht | empfohlen | optional |
| Transparenz gegenüber Nutzer:in | Pflicht | Pflicht | empfohlen |
| Menschliche Aufsicht | Pflicht | empfohlen | optional |

### 3. GPAI-Pflichten (General Purpose AI)
Wenn unsere Kund:innen Foundation Models nutzen (Claude, GPT, Mistral, Llama), sind die GPAI-Pflichten primär beim Modell­anbieter. Wir dokumentieren, welche Modelle für welchen Zweck eingesetzt werden — für die nachgelagerte Konformitäts­dokumentation.

## Praktische Auswirkung

In der Mehrzahl unserer Projekte (interne RAG-Systeme, KI-Agenten für Geschäfts­prozesse, Personal Assistants) greift "begrenztes Risiko" mit Transparenz­pflicht. Das ist gut beherrschbar.

Hochrisiko-Projekte (z.B. HR-Screening-Systeme) lehnen wir nicht ab — aber wir steigen nicht ohne juristischen Mitstreiter ein und planen den Konformitäts­bewertungs­aufwand realistisch.

## Was wir liefern

- AI-Act-Klassifikations­analyse pro Projekt (Teil des Discovery-Workshops und des Readiness-Assessments)
- Logging-Architektur, die AI-Act-tauglich ist
- Modell-Karten / System-Karten zu eingesetzten KI-Komponenten
- Übergabe-Doku, die DSB und externe Auditoren nicht zur Verzweiflung treibt

## Wo wir Grenzen ziehen

- Wir sind Engineers, keine Juristen. Bei komplexen Fragen kooperieren wir mit Fach­anwält:innen.
- Bei Hochrisiko-Systemen mit hoher Konformitäts­bewertungs­last (z.B. Medizin­produkte nach MDR + AI Act) gibt es spezialisiertere Häuser.

**Verwandt:**
- DSGVO-Positionierung: `compliance/dsgvo-positioning.md`
- Datenresidenz: `compliance/data-residency.md`
