---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: openai
---

# OpenAI — Preise

Alle Angaben Stand 2026-05-20, in USD pro 1 Million Token (sofern nicht anders angegeben). Verbindliche Preise immer auf der Pricing-Seite verifizieren [Quelle: https://openai.com/api/pricing/] [Quelle: https://developers.openai.com/api/docs/pricing].

## GPT-5-Familie (aktuell)

| Modell | Input | Cached Input | Output | Kontext |
|---|---|---|---|---|
| GPT-5.5 | 5,00 USD | 0,50 USD | 30,00 USD | 1M |
| GPT-5.5 Pro | 30,00 USD | — | 180,00 USD | 1M |
| GPT-5.4 | 2,50 USD | 0,25 USD | 15,00 USD | 1M |
| GPT-5.4 Mini | 0,75 USD | 0,075 USD | 4,50 USD | 400K |
| GPT-5.4 Nano | 0,20 USD | 0,02 USD | 1,25 USD | 400K |
| GPT-5.2-Codex | 1,75 USD | 0,175 USD | 14,00 USD | 400K |

## GPT-5-Vorgänger / Legacy

| Modell | Input | Output | Kontext |
|---|---|---|---|
| GPT-5 | 1,25 USD | 10,00 USD | 400K |
| GPT-5 Mini | 0,25 USD | 2,00 USD | 400K |
| GPT-4o | 2,50 USD | 10,00 USD | 128K |
| GPT-4o mini | 0,15 USD | 0,60 USD | 128K |

## o-Linie (Reasoning)

| Modell | Input | Output | Kontext |
|---|---|---|---|
| o3-pro | 20,00 USD | 80,00 USD | 200K |
| o3 | 2,00 USD | 8,00 USD | 200K |
| o3-mini | 1,10 USD | 4,40 USD | 200K |

Reasoning-Modelle nutzen zusätzlich "Reasoning Tokens" (intern), die ebenfalls als Output abgerechnet werden — Kosten können real deutlich höher liegen [Quelle: https://platform.openai.com/docs/guides/reasoning].

## Embeddings

| Modell | Standard / 1M Token | Batch / 1M Token |
|---|---|---|
| `text-embedding-3-small` | 0,02 USD | 0,01 USD |
| `text-embedding-3-large` | 0,13 USD | 0,065 USD |
| `text-embedding-ada-002` | 0,10 USD | 0,05 USD |

## Audio / Image

- **Whisper**: 0,006 USD pro Audio-Minute [Quelle: https://platform.openai.com/docs/guides/speech-to-text]
- **GPT-4o Transcribe**: 2,50 USD/1M Input, 10,00 USD/1M Output, oder 0,006 USD/Minute
- **TTS Standard**: 15 USD pro 1M Zeichen
- **TTS HD**: 30 USD pro 1M Zeichen
- **gpt-4o-mini-tts**: 0,60 USD/1M Text-Input + 12 USD/1M Audio-Output (~0,015 USD/min)
- **DALL-E / GPT-Image**: tiered nach Qualität und Auflösung — Details siehe offizielle Pricing-Seite

## Rabatte und Sonderpreise

- **Batch und Flex**: 50% Rabatt für asynchrone Jobs (<24h SLA) [Quelle: https://platform.openai.com/docs/guides/batch]
- **Priority**: 2,5x Preisaufschlag für garantierte Kapazität
- **Cached Input**: Automatisches Caching wiederholter Prompts (kein Setup nötig), GPT-5.5 = 90% Rabatt (0,50 statt 5,00), GPT-5.4 = 90% Rabatt
- **Scale Tier / Enterprise**: Volumenrabatte, dedizierte Kapazität — auf Anfrage
- **Azure OpenAI**: Eigene Preisliste, oft minimal höher, dafür EU-Hosting und Enterprise-Vertragswerk [Quelle: https://azure.microsoft.com/en-us/pricing/details/cognitive-services/openai-service/]

## Rate Limits

- Tier-System (Tier 1-5), das mit kumuliertem Umsatz wächst [Quelle: https://platform.openai.com/docs/guides/rate-limits]
- Tier 1 (Default): begrenzte RPM/TPM — konkrete Werte modellspezifisch, vor Production-Deployment in der Console prüfen
- Tier 5: bis zu Millionen TPM, für Production-Workloads relevant
