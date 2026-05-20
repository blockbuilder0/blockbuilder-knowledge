---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: openai
---

# OpenAI — Quellen

Alle URLs abgerufen 2026-05-20.

## Offizielle Quellen

- **Hauptseite**: https://openai.com
- **Plattform**: https://platform.openai.com
- **Modelle**: https://platform.openai.com/docs/models
- **API-Docs**: https://platform.openai.com/docs
- **Pricing**: https://openai.com/api/pricing/
- **Realtime API**: https://platform.openai.com/docs/guides/realtime
- **Embeddings**: https://platform.openai.com/docs/guides/embeddings
- **Reasoning Guide**: https://platform.openai.com/docs/guides/reasoning
- **Batch API**: https://platform.openai.com/docs/guides/batch
- **Fine-Tuning**: https://platform.openai.com/docs/guides/fine-tuning
- **Rate Limits**: https://platform.openai.com/docs/guides/rate-limits
- **Trust Portal**: https://trust.openai.com
- **EU DPA**: https://openai.com/policies/eu-data-processing-addendum
- **Datennutzung**: https://platform.openai.com/docs/models/how-we-use-your-data

## Azure OpenAI (EU-Pfad)

- **Hauptseite**: https://azure.microsoft.com/en-us/products/ai-services/openai-service
- **Pricing**: https://azure.microsoft.com/en-us/pricing/details/cognitive-services/openai-service/
- **Docs**: https://learn.microsoft.com/en-us/azure/ai-services/openai/
- **Data Privacy**: https://learn.microsoft.com/en-us/azure/ai-services/openai/data-privacy
- **Compliance**: https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/legal-and-privacy

## SDKs

- **Python**: https://github.com/openai/openai-python
- **Node**: https://github.com/openai/openai-node

## Verifizierte Fakten (Stand 2026-05-20)

- **Aktuelle GPT-5-Familie (Azure-Foundry-Sicht)**: GPT-5.5 (`gpt-5.5`, 04/2026), GPT-5.4 (`gpt-5.4`, `-mini`, `-nano`, `-pro`), GPT-5.3 (`-chat`, `-codex`), GPT-5.2 (`-codex`, `-chat`), GPT-5.1 (`-chat`, `-codex`, `-codex-mini`, `-codex-max`), GPT-5 (`-mini`, `-nano`, `-chat`, `-codex`, `-pro`); 1M Kontext für Reasoning-Linie, 400k für Mainstream-Reasoning [Quelle: https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models, abgerufen 2026-05-20]
- **o-Serie**: `o3` (04/2025) und `o3-pro` (06/2025) weiterhin aktiv neben GPT-5-Thinking [Quelle: https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models, abgerufen 2026-05-20]
- **OpenAI-Produkt-Bezeichnungen (Wikipedia)**: gpt-5-main, gpt-5-main-mini, gpt-5-thinking, gpt-5-thinking-mini, gpt-5-thinking-nano (API-only), gpt-5-thinking-pro [Quelle: https://en.wikipedia.org/wiki/GPT-5, abgerufen 2026-05-20]

## Noch zu prüfen (openai.com blockt WebFetch mit HTTP 403)

- Exakte Pricing-Werte aller Modelle in USD/1M Token *(Stand 2026-05-20: https://openai.com/api/pricing/ und https://platform.openai.com/docs/pricing liefern HTTP 403 für automatisierte Abrufe — vor Kunden-Quote manuell verifizieren)*
- Exakte Embedding-Preise und Dimensionen-Optionen für `text-embedding-3-small` / `-large` *(Stand 2026-05-20: docs.openai.com 403 — manuell verifizieren; bekannt sind 1536 (small) und 3072 (large) Default-Dimensionen mit Matryoshka-Truncation)*
- Default-Rate-Limits per Tier 1–5 *(Stand 2026-05-20: help.openai.com 403 — manuell verifizieren)*
- Azure OpenAI EU-Regionen für die jeweils neueste Modell-Generation *(Stand 2026-05-20: Azure-Doku-Seite ist sehr umfangreich; pro Modell-ID auf der Foundry-Models-Seite die `Region availability`-Tabelle prüfen; GPT-5.x ist auf Tier-5/Tier-6-Subscriptions oft quota-pflichtig)*
