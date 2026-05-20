---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: mistral
---

# Mistral — Modellvarianten

Stand 2026-05-20. Mistral ändert Produktnamen und Versionen regelmäßig — vor Quote verifizieren [Quelle: https://docs.mistral.ai/getting-started/models/models_overview/].

## Frontier (Generalist, Multimodal)

| Modell | Version | Parameter | Kontext | Lizenz | Einsatz |
|---|---|---|---|---|---|
| **Mistral Large 3** | v25.12 | nicht offen ausgewiesen (Open-Weight) | 128K | Open / kommerziell | State-of-the-Art multimodal [Quelle: https://mistral.ai/news/mistral-large-2407/] |
| **Mistral Medium 3.5** | v3.5 / v26.03 | k.A. | 128K | Open | Frontier-Multimodal für Agenten/Coding |
| **Mistral Medium 3.1** | v25.08 | k.A. | 128K | Premier | Balance Qualität/Kosten |
| **Mistral Small 4** | v26.03 | 24B (basiert auf Small-3-Linie) | 128K | Open | Hybrid (instruct + reasoning + coding) |
| **Mistral Small 3.1** | v25.03 | 24B | 128K | Apache 2.0 | Vorgänger Small 4, weiterhin produktiv |
| **Mistral Small 3** | v25.01 | 24B | 32K | Apache 2.0 | On-Prem-Default, RTX 4090 / 32GB MacBook fähig [Quelle: https://mistral.ai/news/mistral-small-3/] |
| **Magistral Medium 1.2** | v25.09 | k.A. | k.A. | Premier | Frontier multimodales Reasoning |

## Kompakt (Edge / On-Device)

| Modell | Version | Parameter | Kontext | Lizenz |
|---|---|---|---|---|
| **Ministral 3 14B** | v25.12 | 14B | 128K | Open |
| **Ministral 3 8B** | v25.12 | 8B | 128K | Open [Quelle: https://mistral.ai/news/ministraux/] |
| **Ministral 3 3B** | v25.12 | 3B | 128K | Open |

## Spezialist

| Modell | Version | Parameter | Spezialisierung | Lizenz |
|---|---|---|---|---|
| **Devstral 2** | v25.12 | k.A. | Code-Agenten, Software Engineering | Open |
| **Codestral** | v25.08 | k.A. | Code-Generierung, Fill-in-the-Middle (256K Kontext) | Premier [Quelle: https://mistral.ai/news/codestral/] |
| **Pixtral Large** | 2411 | 124B | Vision-Language (131K Kontext) | Open |
| **Pixtral 12B** | — | 12B | Vision-Language (128K) | Apache 2.0 [Quelle: https://mistral.ai/news/pixtral-12b/] |
| **Mistral Saba** | 2502 | 24B | Arabisch + südasiatische Sprachen (32K) | Premier [Quelle: https://mistral.ai/news/mistral-saba] |
| **Mistral NeMo** | v24.07 | 12B | Mehrsprachig, mit NVIDIA (128K) | Apache 2.0 [Quelle: https://mistral.ai/news/mistral-nemo/] |
| **Mathstral 7B** | — | 7B | Mathematik (32K) | Apache 2.0 |
| **OCR 3** | v25.12 | k.A. | Dokument-OCR | Premier |
| **Leanstral** | v26.03 | k.A. | Labs / Open-source Experiment | Open |
| **Voxtral TTS** | v26.03 | k.A. | TTS mit Zero-Shot Voice-Cloning | Open |
| **Voxtral Small / Mini Transcribe** | v25.07 / v26.02 | k.A. | ASR | Open / Premier |
| **Mistral Moderation 2** | v26.03 | k.A. | Content-Moderation, 128K Kontext | Premier |
| **Mixtral 8x7B / 8x22B** | — | 46,7B / 141B MoE | Ältere MoE-Generation | Apache 2.0 |

## Embeddings

- **`mistral-embed`** — 1024-Dim Embeddings über La Plateforme [Quelle: https://docs.mistral.ai/capabilities/embeddings/]
- **`codestral-embed`** (v25.05) — Code-spezifische Embeddings, Premier

## Fähigkeiten

- **Sprachen**: Native Mehrsprachigkeit (EN/FR/DE/ES/IT) — gleichbleibend gute Qualität. Saba speziell für Arabisch/Südasien
- **Tool-Use**: Function-Calling via JSON-Schema, OpenAI-kompatibles Format [Quelle: https://docs.mistral.ai/capabilities/function_calling/]
- **JSON-Mode / Structured Outputs**: supported
- **Fine-Tuning**: La Plateforme bietet Fine-Tuning für Open- und Closed-Modelle [Quelle: https://docs.mistral.ai/capabilities/finetuning/]
- **Cost Band**: Insgesamt eines der besten Preis/Leistungs-Verhältnisse im Markt
