---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: anthropic-claude
---

# Claude — Preise

Alle Angaben Stand 2026-05-20, in USD pro 1 Million Token. Verbindliche Preise immer auf der offiziellen Pricing-Seite prüfen [Quelle: https://claude.com/pricing] [Quelle: https://platform.claude.com/docs/en/about-claude/pricing].

## API-Preise (Listenpreise)

| Modell | Input | Output | 5min Cache Write | 1h Cache Write | Cache Hit (Read) |
|---|---|---|---|---|---|
| Claude Haiku 4.5 | 1,00 USD | 5,00 USD | 1,25 USD | 2,00 USD | 0,10 USD |
| Claude Sonnet 4.6 | 3,00 USD | 15,00 USD | 3,75 USD | 6,00 USD | 0,30 USD |
| Claude Opus 4.7 | 5,00 USD | 25,00 USD | 6,25 USD | 10,00 USD | 0,50 USD |

Hinweis: Opus 4.7 hat einen neuen Tokenizer (release 16.04.2026) — bis zu 35% mehr Tokens pro gleichem Text als Opus 4.6, der Preis pro Token bleibt aber identisch [Quelle: https://platform.claude.com/docs/en/about-claude/pricing].

## Wichtige Rabatt-Mechanismen

- **Prompt Caching**: Cache Read = 0,1x Base Input (90% Rabatt). Cache Write = 1,25x (5min) oder 2x (1h). Pays off ab 1. Read bei 5min, ab 2. Read bei 1h [Quelle: https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching]
- **Batch API**: 50% Rabatt auf Input und Output für asynchrone Jobs (<24h SLA). Beispiele: Sonnet 4.6 Batch = 1,50 USD Input / 7,50 USD Output [Quelle: https://platform.claude.com/docs/en/about-claude/pricing]
- **1M-Kontext (Beta)**: Sonnet 4.6, Opus 4.6, Opus 4.7 und Claude Mythos Preview unterstützen 1M Token bei Standard-Preisen (keine Premium-Stufe) [Quelle: https://platform.claude.com/docs/en/about-claude/pricing]
- **Fast Mode (Beta)**: 6x Standard für Opus 4.6/4.7 (30 USD Input / 150 USD Output) — Premium-Latenz, nicht mit Batch kombinierbar

## Bezugswege und Vertragsmodelle

- **Direkte API (claude.com)**: Pay-as-you-go in USD, Rechnung via Stripe, kein Mindestumsatz
- **AWS Bedrock**: Abrechnung über AWS-Account (EUR möglich), EU-Region Frankfurt verfügbar, DPA via AWS Standard. Regional Endpoints +10% Premium ab Modell 4.5
- **Google Vertex AI**: Abrechnung über GCP, EU-Regionen verfügbar. Regional/Multi-Region Endpoints +10% Premium ab Modell 4.5
- **Claude Platform on AWS**: Neue AWS-Marketplace-Variante mit Claude Consumption Units (CCU, 100 CCU = 1 USD). Postpaid-Modell
- **Anthropic Enterprise**: Custom Contracts mit Volume Discounts, dediziertem Support, DPA/BAA-Optionen — Konditionen bei Sales erfragen
- **Data Residency (US-only)**: 1,1x Multiplikator via `inference_geo: "us"` ab Modell 4.6

## Web Search & Tools

- **Web Search**: 10 USD pro 1.000 Suchen + Standard-Token-Kosten
- **Web Fetch**: Keine Zusatzkosten, nur Standard-Token
- **Code Execution**: 1.550 Stunden/Monat frei, dann 0,05 USD/Stunde pro Container

## Praxis-Beispiel (BlockBuilder-typisch)

Heckmair Ada Professional Chatbot mit ca. 50.000 Anfragen/Monat, ca. 8K Context (RAG) + 500 Token Output, Sonnet 4.6:
- Ohne Cache: 50k * (8k * 3 + 0,5k * 15) / 1M = ca. 1.575 USD/Monat
- Mit Prompt Cache auf System+RAG: realistisch 80% Ersparnis -> ca. 320 USD/Monat
