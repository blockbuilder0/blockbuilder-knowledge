---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: mistral
---

# Mistral AI

## Was ist das?

Mistral AI ist ein französischer LLM-Anbieter (gegründet 2023 in Paris) mit dem strategisch wichtigsten Profil im EU-AI-Markt: **EU-Anbieter, EU-Hosting, viele open-weights Modelle**. Mistral kombiniert kommerzielle Closed-Modelle (Large, Medium) mit Open-Source-Veröffentlichungen (Small, NeMo, Ministral, Codestral, Pixtral) [Quelle: https://mistral.ai].

## Warum wir Mistral einsetzen

- **EU-Souveränität**: Mistral La Plateforme hostet in der EU (Frankreich), kein US-Hyperscaler nötig. Für DSGVO-strenge DACH-Kunden oft die einfachste Antwort [Quelle: https://mistral.ai/news/la-plateforme/]
- **Open-Weights**: Mistral Small (Apache 2.0), Codestral, Pixtral, NeMo und Ministral sind frei herunterladbar — wir können on-prem oder air-gapped deployen
- **Microsoft-Azure-Partnerschaft**: Mistral Large ist auch in Azure AI Foundry (EU-Regionen) verfügbar [Quelle: https://learn.microsoft.com/en-us/azure/ai-foundry/foundry-models/]
- **Multilingual stark**: Deutsch, Französisch, Spanisch, Italienisch nativ trainiert — keine "Englisch-zuerst"-Verzerrung
- **Le Chat**: ChatGPT-Alternative aus EU, für Endanwender-Vergleichbarkeit relevant [Quelle: https://chat.mistral.ai]

## Wie wir Mistral integrieren

- **Mistral Small on Ollama** als Default-on-prem-LLM für Kunden mit Datenschutz-Bedenken (z. B. Anwaltskanzleien)
- **Mistral Large via La Plateforme** wenn EU-Cloud akzeptabel ist
- **Codestral** als Code-Assistant-Backend in Coding-PoCs
- **Pixtral** für multimodale Use-Cases (Belegextraktion) als on-prem Alternative zu GPT-4o Vision
- **Mistral Inference / vLLM** für skalierbare On-Prem-Production-Deployments

## Wofür eignet sich Mistral NICHT?

- **Absolute Top-Reasoning** (komplexe Mathematik, Multi-Step-Agenten): Claude Opus 4.7 und OpenAI GPT-5-Thinking / o3 liegen Stand 2026-05-20 vorn [Quelle: https://platform.claude.com/docs/en/docs/about-claude/models, https://en.wikipedia.org/wiki/GPT-5, abgerufen 2026-05-20]
- **Native Multimodalität mit Audio**: Pixtral kann Bilder, aber kein Audio-I/O — kein Realtime-Voice
- **Eingebautes State-of-the-Art Embedding-Modell**: `mistral-embed` existiert, ist aber kein Default in der RAG-Community [Quelle: https://docs.mistral.ai/capabilities/embeddings/]
- **Ecosystem-Reife**: Tools, SDKs und Integrationen sind solide, aber weniger reichhaltig als OpenAI-Welt
- **Computer-Use / Vollintegrierte Agents**: Anthropic-Niveau noch nicht erreicht
