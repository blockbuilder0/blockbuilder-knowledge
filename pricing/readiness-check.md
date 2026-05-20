# AI-Readiness-Check

6 Fragen, konkrete Empfehlung mit Preisband — bevor der erste Call stattfindet. Frei zugänglich auf [block-builder.de/de/estimator](https://block-builder.de/de/estimator), kein E-Mail-Gate.

## Was der Check liefert

Statt eines Fantasie-EUR-Betrags bekommst du:

1. Eine konkrete **Empfehlung** (einer von 6 Pfaden, siehe unten)
2. Ein realistisches **Preisband** mit Festpreis-Anker wo möglich
3. Einen klaren **nächsten Schritt** (Workshop buchen, Discovery-Call, Assessment)

Das Tool ist ehrlich genug, "noch zu früh, lass uns 30 Minuten reden" als Empfehlung auszugeben — und schickt dich nicht in jedem Fall auf eine teure Implementierung.

## Die 6 Fragen

1. **Use-Case-Familie**: Custom Agent · RAG / Semantische Suche · Self-hosted LLM · Dokumenten­verarbeitung & OCR · Voice / Avatar-UI · Andere/unklar
2. **Datenresidenz**: On-Premise · EU-Cloud (DE/AT) · Global Cloud OK · Hybrid · Noch unklar
3. **AI-Reifegrad**: Noch nichts · Experimentieren intern · Pilot läuft · In Production · Skalierung
4. **Größte Hürden** (max. 3): DSGVO / Compliance · Kosten · Fehlende interne Expertise · Unklarer ROI · Integration in bestehende Systeme · Daten­qualität
5. **Timeline**: POC in 2–3 Wochen · Pilot in 2–3 Monaten · 6+ Monate Strategie · Noch zu früh
6. **Unter­nehmens­größe**: Solo (1) · 2–10 · 11–50 · 51–250 · 250+

## Die 5+1 möglichen Empfehlungen

| Empfehlung | Dauer | Preis | Wann |
|---|---|---|---|
| **Solo-AI-Workshop** | 3 Stunden | 480 EUR netto Festpreis | Solo-Selbstständige, die KI im Alltag nutzen wollen |
| **AI-Discovery-Workshop** | 1–2 Tage | ab 1.500 EUR Festpreis | Erste Sortierung, Quick-Wins, 90-Tage-Roadmap |
| **AI-Readiness-Assessment** | 1–2 Wochen | ab 3.500 EUR Festpreis | Strukturierte Analyse, Risk-Map, Stack-Empfehlung |
| **AI-Pilot (Working Prototype)** | 8 Wochen | ab 18.000 EUR Festpreis | Vom Use-Case zum lauffähigen Prototyp, Go/No-Go-Entscheidung |
| **AI-Implementierung in Production** | 3–6 Monate | T&M oder Festpreis nach Scoping | End-to-End-Umsetzung in den Produktiv­betrieb |
| **Kostenfreier Discovery-Call** | 30 Min | kostenlos | Wenn der Check ergibt: "noch zu früh oder unklar" |

## Was du NICHT bekommst

- Kein Sales-Funnel mit "Demo-Anfrage" als Voraussetzung für Preis-Info
- Keine "Custom Enterprise Plan, bitte kontaktieren" für KMU-Use-Cases
- Keine Mondpreise, kein Verhandlungs­theater

## Wie die Empfehlungs­logik funktioniert

Vereinfacht (siehe Source-Code für Details):

- **Solo + noch nichts** → Solo-Workshop
- **Solo + experimentiert schon** → Discovery-Workshop
- **Mikro (2–10) + Compliance/ROI-Sorgen** → Assessment
- **KMU + 2–3 Monate Timeline + Pilot läuft** → Pilot
- **Mittel/Groß + In Production / Skalierung** → Implementierung
- **Sonst** → Kostenfreier Discovery-Call

**Verwandt:**
- Engagement-Modelle: `pricing/engagement-models.md`
- Pricing-Philosophie: `pricing/pricing-philosophy.md`
- Consulting-Service: `services/consulting-training.md`
- Direkter Link: https://block-builder.de/de/estimator
