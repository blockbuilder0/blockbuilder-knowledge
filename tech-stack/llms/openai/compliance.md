---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: openai
---

# OpenAI — Compliance für DACH-B2B

Stand 2026-05-20. Verbindliche Aussagen mit dem OpenAI Trust Portal und Azure OpenAI Compliance-Dokumenten abgleichen [Quelle: https://trust.openai.com].

## DSGVO / GDPR

- **DPA**: OpenAI stellt einen DPA für API-Kunden bereit (Self-Service-Annahme im Account-Dashboard) [Quelle: https://openai.com/policies/eu-data-processing-addendum]
- **Datenresidenz**: OpenAI Direct API verarbeitet in den USA. Für **EU-Datenresidenz** ist **Azure OpenAI in EU-Regionen** (z. B. France Central, Sweden Central, Germany West Central) der empfohlene Pfad
- **Kein Training auf API-Daten**: API-Inputs/Outputs werden per Default **nicht** zum Training verwendet [Quelle: https://platform.openai.com/docs/models/how-we-use-your-data]
- **Retention**: 30 Tage Default-Logging für Trust&Safety, Zero Data Retention vertraglich verfügbar für qualifizierte Use-Cases [Quelle: https://platform.openai.com/docs/models/default-usage-policies-by-endpoint]
- **EU Data Boundary** (Azure): Microsoft garantiert Datenverarbeitung innerhalb der EU/EFTA für Azure OpenAI EU-Deployments [Quelle: https://learn.microsoft.com/en-us/azure/ai-services/openai/data-privacy]

## EU AI Act

- OpenAI-Modelle gelten als GPAI; GPT-5/o3-Klasse fallen vermutlich in "GPAI mit systemischem Risiko"
- OpenAI veröffentlicht Model Cards und Safety Evaluations [Quelle: https://openai.com/safety]
- Deployer-Pflichten (Transparenz Art. 50, Hochrisiko-Klassifizierung) bleiben beim Kunden

## Zertifikate

- **SOC 2 Type II** (OpenAI direkt)
- **ISO 27001, ISO 27018, ISO 27701** (Azure OpenAI über Microsoft) [Quelle: https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/legal-and-privacy]
- **BSI C5** über Azure-Infrastruktur

## Bezugswege im Vergleich

| Pfad | Datenresidenz | DPA | Zertifikate | Empfehlung |
|---|---|---|---|---|
| OpenAI Direct API | US | ja | SOC 2 | nur für interne PoCs / unkritische Daten |
| **Azure OpenAI EU** | EU (DE/FR/SE) | über MS DPA | C5, ISO27001/27018, SOC2 | **Default für DACH-Production** |

## Branchen-Eignung

- **Finanzen / Versicherung**: über Azure OpenAI realisierbar; BaFin-Auslagerungsanzeige nötig
- **Gesundheit**: Azure OpenAI mit zusätzlicher Verschlüsselung; § 203-StGB-Prüfung kritisch
- **Anwaltskanzleien**: Wir empfehlen on-prem (Mistral/Ollama) statt OpenAI
- **Öffentliche Hand**: Azure OpenAI mit BSI C5 darstellbar; IT-Grundschutz-Mapping individuell
