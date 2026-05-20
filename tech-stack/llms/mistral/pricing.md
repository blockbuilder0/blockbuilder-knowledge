---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: mistral
---

# Mistral — Preise

Stand 2026-05-20, in USD pro 1M Token (La Plateforme). Verbindlich auf Pricing-Seite verifizieren [Quelle: https://mistral.ai/pricing] [Quelle: https://docs.mistral.ai/getting-started/models/models_overview/].

## La Plateforme (kommerzielle API)

| Modell | Input | Output | Kontext |
|---|---|---|---|
| Mistral Large 3 | 2,00 USD | 6,00 USD | 128K |
| Mistral Medium 3.5 | 1,00 USD | 3,00 USD | 128K |
| Mistral Medium 3.1 | 0,40 USD | 2,00 USD | 128K |
| Mistral Small 4 / Small 3.1 (managed) | 0,20 USD | 0,60 USD | 128K |
| Codestral (v25.08) | 0,30 USD | 0,90 USD | 256K |
| Pixtral Large (2411) | 2,00 USD | 6,00 USD | 131K |
| Ministral 3 8B | 0,10 USD | 0,10 USD | 128K |
| Ministral 3 3B | 0,04 USD | 0,04 USD | 128K |
| Mistral Saba | 0,20 USD | 0,60 USD | 32K |
| `mistral-embed` | 0,10 USD | — | — |
| `codestral-embed` | 0,15 USD | — | — |

Hinweis: Mistral Medium 3.5 (v3.5) ist das aktuelle Multimodal-Flagship für agentische und Coding-Use-Cases. Medium 3.1 bleibt als günstigerer Premier-Tier verfügbar [Quelle: https://docs.mistral.ai/getting-started/models/models_overview/].

## Open-Weights (selbst hosten)

- **Lizenz**: Apache 2.0 für Small/Medium 3.5/Large 3/NeMo/Ministral/Pixtral/Mathstral/Devstral — frei kommerziell nutzbar
- **Codestral**: Premier-Modell, La-Plateforme-only; keine offene Lizenz für Production [Quelle: https://mistral.ai/news/codestral/]
- **Inferenzkosten** = Hardware + Strom + Ops. Bei On-Prem über Ollama oder vLLM
- **Beispielrechnung**: Mistral Small 3 / 3.1 / 4 (24B) läuft auf 1x RTX 4090 (24GB) ausreichend für mittlere Last; auf 1x A100 80GB komfortabel mit hoher Throughput

## Azure AI Foundry (EU-Pfad)

- Mistral Large via Azure: getrennte Preisliste, oft minimal höher als La Plateforme, dafür Azure-Vertragswerk und EU-Regionen [Quelle: https://learn.microsoft.com/en-us/azure/ai-foundry/foundry-models/]
- Abrechnung in EUR möglich, Microsoft-DPA

## Le Chat (Endanwender)

- **Free Tier** verfügbar
- **Pro / Team / Enterprise** mit Zusatzfeatures, EUR-Tarife [Quelle: https://mistral.ai/pricing]

## Rabatte

- **Batch API**: 50% Rabatt auf Compute-Kosten für asynchrone Inferenz [Quelle: https://docs.mistral.ai/capabilities/batch/, abgerufen 2026-05-20]
- **Enterprise / Dedicated Capacity**: auf Anfrage
