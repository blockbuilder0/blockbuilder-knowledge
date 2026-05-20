# On-Premise AI

DSGVO-konforme KI auf kundeneigener Hardware oder in dedizierten EU-Rechenzentren. Zwei Lieferpfade, beide mit voller Datenkontrolle.

URL: https://block-builder.de/de/services/on-premise-ai

## Zwei Wege

### On-Premise (eigene Hardware)
- Einmalige Hardware-Investition ab ca. 15.000 EUR
- Laufende Kosten (Strom, Wartung) ca. 300 EUR/Monat
- Setup-Zeit 2–4 Wochen
- Break-Even gegenüber Cloud nach ca. 18 Monaten
- Ideal: eigenes IT-Team vorhanden, langfristige Nutzung (3+ Jahre), Daten dürfen das Gebäude nicht verlassen

### Cloud-Hosted (dediziert in DE-Rechenzentrum)
- Keine Investition
- Monatliche Miete ab 499 EUR
- Setup-Zeit 3–7 Tage
- AVV inklusive, EU-Rechenzentrum
- Ideal: kein eigenes IT-Team, schneller Start, flexible Skalierung

## Was wir liefern

- **Lokale LLMs**: Llama, Mistral, Qwen — laufen auf eigener Hardware oder dedizierter Cloud-Instanz
- **Fine-Tuning** auf Unternehmensdaten
- **RAG-Systeme** über interne Wissensbasen
- **AVV-konforme Architektur** mit Audit-Trails

## Typische Use-Cases

- Interne Dokumentensuche und -analyse
- Automatisierte E-Mail-Bearbeitung
- Kundenservice-Chatbots mit Unternehmenswissen
- Code-Generierung und -Review
- Datenextraktion aus Dokumenten
- KI-Agenten für Geschäftsprozesse

## Wofür eignet sich On-Premise AI NICHT?

Wer **maximale Modellqualität** braucht (z.B. GPT-4-Klasse für komplexe Reasoning-Aufgaben) und die Compliance-Frage anders lösen kann (DPA mit OpenAI/Anthropic, Azure-OpenAI in EU-Region), fährt mit gehosteten Frontier-Modellen oft günstiger und schneller. On-Premise lohnt sich, wenn Datenresidenz harte Anforderung ist oder Token-Volumen so hoch wird, dass APIs teurer werden als eigene GPUs. Für reine **One-off-Experimente** ohne klare Skalierungsperspektive ist die Hardware-Investition Overkill — dann lieber Cloud-Hosted oder direkt API.

## Preisorientierung

| Modell | Initial | Laufend |
|---|---|---|
| On-Premise | ab ~15.000 EUR Hardware | ~300 EUR/Monat |
| Cloud-Hosted | keine | ab 499 EUR/Monat |
| Implementierung | nach Scoping | — |

**Verwandt:**
- Self-Hosting-Tooling: `tech-stack/self-hosting.md`
- Infrastruktur-Optionen: `tech-stack/infrastructure.md`
- Entscheidung On-Prem vs Cloud: `decision-matrices/on-premise-vs-cloud-ai.md`
- DSGVO-Positionierung: `compliance/dsgvo-positioning.md`
- Mehr dazu: https://block-builder.de/de/services/on-premise-ai
