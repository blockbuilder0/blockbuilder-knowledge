---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: openai
---

# OpenAI

## Was ist das?

OpenAI ist der US-Anbieter, der mit GPT-3 (2020) und ChatGPT (Nov 2022) die LLM-Welle ausgelöst hat. Die Produkt-Familie umfasst die **GPT-4o-Linie** (multimodal), die **o-Linie** (Reasoning: o1, o3 und Nachfolger), **Embeddings** (`text-embedding-3-small/large`), **Whisper** (Speech-to-Text), **TTS**, **DALL-E / GPT-Image** (Image-Gen), die **Realtime API** (Voice) und die **Assistants/Responses-API** [Quelle: https://platform.openai.com/docs].

## Warum wir OpenAI einsetzen

- **Multimodalität**: GPT-4o akzeptiert Text, Bild und Audio nativ; Realtime API liefert sub-300ms Voice-Latenz — für Voicebots ist OpenAI Stand 2026-05-20 die erste Wahl [Quelle: https://platform.openai.com/docs/guides/realtime]
- **Reasoning-Spitze**: Die o-Serie (o3, o3-pro, weiterhin aktiv) und die GPT-5-Thinking-Familie (gpt-5-thinking, -mini, -nano, -pro) liefern State-of-the-Art bei mathematischem und wissenschaftlichem Reasoning [Quelle: https://en.wikipedia.org/wiki/GPT-5, https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models, abgerufen 2026-05-20]
- **Embeddings im Standard-Stack**: `text-embedding-3-small` ist günstig, schnell, mehrsprachig — solide Default-Wahl, wenn EU-Residenz nicht zwingend
- **Whisper**: Transkription mit sehr guter Deutsch-Qualität, lokal via `whisper.cpp` oder Cloud-API
- **Marktreife**: Reichste SDK- und Tooling-Welt (LangChain, LlamaIndex, Vercel AI SDK)

## Wie wir OpenAI integrieren

- **Embeddings** in RAG-Pipelines, wenn Kunde Cloud erlaubt und keine EU-Pflicht hat — sonst `nomic-embed-text` via Ollama lokal
- **Whisper API** für Voice-Workflows (Meeting-Transkripte, Call-Center)
- **Realtime API** für prAIvicy-Voicebot-Prototypen
- **GPT-4o** als Fallback im prAIvicy-Gateway, wenn ein Use-Case explizit Audio/Image-Generation braucht — für Reasoning-Defaults setzen wir Claude

## Wofür eignet sich OpenAI NICHT?

- **On-Premise**: Geschlossene Modelle, nicht selbst hostbar. Azure OpenAI ist Cloud-only, kein Edge-Deployment
- **Strikte DSGVO ohne Cloud**: Direkter API-Zugang ist US-only; EU-Residenz nur über **Azure OpenAI Service in EU-Regionen** [Quelle: https://learn.microsoft.com/en-us/azure/ai-services/openai/]
- **Datenschutz-sensible Branchen ohne BAA-Äquivalent**: § 203 StGB-Pflichten (Anwälte, Ärzte) lassen sich rechtssicher nur mit on-prem-Lösungen umsetzen
- **Sehr lange Kontexte (>200K)**: GPT-4o liegt bei 128K, deutlich unter Claude Opus 1M-Beta
- **Open-Source Compliance**: Wer Modelle inspizieren / fine-tunen / portieren können muss, ist mit Mistral oder Llama besser bedient
