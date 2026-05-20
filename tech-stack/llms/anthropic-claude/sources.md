---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: anthropic-claude
---

# Claude — Quellen

Alle URLs abgerufen 2026-05-20.

## Offizielle Quellen

- **Hauptseite**: https://www.anthropic.com/claude
- **Modellübersicht**: https://docs.anthropic.com/en/docs/about-claude/models
- **API-Dokumentation**: https://docs.anthropic.com
- **Pricing**: https://www.anthropic.com/pricing
- **Prompt Caching**: https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching
- **Batch API**: https://docs.anthropic.com/en/docs/build-with-claude/batch-processing
- **Tool Use**: https://docs.anthropic.com/en/docs/build-with-claude/tool-use
- **Computer Use**: https://docs.anthropic.com/en/docs/build-with-claude/computer-use
- **Commercial Terms**: https://www.anthropic.com/legal/commercial-terms
- **Trust Center**: https://trust.anthropic.com
- **Responsible Scaling Policy**: https://www.anthropic.com/responsible-disclosure-policy

## SDKs

- **Python**: https://github.com/anthropics/anthropic-sdk-python
- **TypeScript**: https://github.com/anthropics/anthropic-sdk-typescript

## Bezugswege

- **AWS Bedrock**: https://aws.amazon.com/bedrock/claude/
- **Google Vertex AI**: https://cloud.google.com/vertex-ai/generative-ai/docs/partner-models/use-claude

## Verifizierte Fakten (Stand 2026-05-20)

- **API-IDs der 4.x-Modelle**:
  - Opus 4.7: `claude-opus-4-7` (dateless gepinnter Snapshot, neuer Tokenizer)
  - Sonnet 4.6: `claude-sonnet-4-6` (dateless gepinnter Snapshot)
  - Haiku 4.5: `claude-haiku-4-5-20251001` (Alias: `claude-haiku-4-5`)
  - Hinweis: Ab 4.6-Generation verwenden API-IDs ein dateless Format, sind aber dennoch gepinnte Snapshots, kein evergreen Pointer [Quelle: https://platform.claude.com/docs/en/docs/about-claude/models, abgerufen 2026-05-20]
- **Listenpreise (USD pro 1M Token, Standard-Tier)**: Opus 4.7: 5 / 25 (in/out); Sonnet 4.6: 3 / 15; Haiku 4.5: 1 / 5 [Quelle: https://platform.claude.com/docs/en/docs/about-claude/models, abgerufen 2026-05-20]

## Noch zu prüfen (vor Kunden-Quote)

- Verfügbarkeit Zero Data Retention (ZDR) für Self-Service-Kunden *(Stand 2026-05-20: nicht öffentlich dokumentiert, manuell zu prüfen — Trust Center und Sales-Kontakt erforderlich)*
- Enterprise-Vertragseintrittsschwelle (USD/Jahr) *(Stand 2026-05-20: nicht öffentlich dokumentiert, manuell zu prüfen)*
- GPT-4o und Mistral Large 2 Preise im Vergleich *(Stand 2026-05-20: Mistral Large 2 ist EOL, durch Mistral Large 3 abgelöst; aktuelle Mistral-Preise siehe Datei `tech-stack/llms/mistral/pricing.md`; OpenAI-Pricing-Seite blockiert WebFetch (HTTP 403), manuell auf https://openai.com/api/pricing/ verifizieren)*
