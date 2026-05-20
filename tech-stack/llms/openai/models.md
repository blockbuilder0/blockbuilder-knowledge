---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: openai
---

# OpenAI — Modellvarianten

Stand 2026-05-20. OpenAI veröffentlicht Modelle in hoher Kadenz; aktuelle IDs vor Deployment auf der Models-Seite verifizieren [Quelle: https://platform.openai.com/docs/models].

## GPT-5-Familie (multimodal, Top-Tier)

| Modell | Kontext | Vision | Audio I/O | Tool-Use | Einsatz |
|---|---|---|---|---|---|
| **GPT-5.5** | 1M | ja | ja | ja | Hard coding, Agenten, anspruchsvolle Aufgaben |
| **GPT-5.5 Pro** | 1M | ja | ja | ja | Höchste Genauigkeit |
| **GPT-5.4** | 1M | ja | ja | ja | Frontier-Qualität, günstiger als 5.5 |
| **GPT-5.4 Mini** | 400K | ja | begrenzt | ja | Production-Routing, günstig |
| **GPT-5.4 Nano** | 400K | ja | nein | ja | Hochvolumen-Klassifizierung |
| **GPT-5.2-Codex** | 400K | ja | nein | ja | Dedizierte Coding-Agenten |

## GPT-4o (Legacy, weiterhin verfügbar)

| Modell | Kontext | Vision | Audio I/O | Tool-Use | Einsatz |
|---|---|---|---|---|---|
| **GPT-4o** | 128K | ja | in+out | ja | Multimodale Chats, Realtime API |
| **GPT-4o mini** | 128K | ja | begrenzt | ja | Günstige Hochvolumen-Klassifizierung |

## o-Linie (Reasoning)

| Modell | Kontext | Thinking | Einsatz |
|---|---|---|---|
| **o3** | 200K | sichtbar | Aktueller Reasoning-State-of-the-Art [Quelle: https://openai.com/index/openai-o3-mini/] |
| **o3-pro** | 200K | sichtbar | Komplexes wissenschaftliches Reasoning |
| **o3-mini** | 200K | sichtbar | Mathematik, kostenoptimiertes Reasoning |

## Embeddings

| Modell | Dimensionen | Mehrsprachig | Empfehlung |
|---|---|---|---|
| `text-embedding-3-small` | 1536 (kürzbar) | ja | **Default für Cloud-RAG** [Quelle: https://platform.openai.com/docs/guides/embeddings] |
| `text-embedding-3-large` | 3072 (kürzbar) | ja | Höchste Retrieval-Qualität, ca. 6x teurer |

## Audio

- **Whisper (`whisper-1`)**: ASR, sehr gute Deutsch-Qualität, 0,006 USD/Minute [Quelle: https://platform.openai.com/docs/guides/speech-to-text]
- **GPT-4o Transcribe**: Neue Transkriptions-Variante, Token- oder Minuten-basiert
- **TTS (`tts-1`, `tts-1-hd`)**: Sprachsynthese, mehrsprachig. HD = 2x Preis von Standard
- **gpt-4o-mini-tts**: Token-basierte TTS mit Audio-Output
- **Realtime API**: bidirektionales Voice-Streaming, GPT-4o-basiert [Quelle: https://platform.openai.com/docs/guides/realtime]

## Bildgenerierung

- **DALL-E 3 / GPT-Image**: Text-zu-Bild, integriert in Chat Completions und Image API [Quelle: https://platform.openai.com/docs/guides/images]

## Fähigkeiten

- **Sprachen**: Sehr gutes Deutsch, fast alle Hauptsprachen abgedeckt
- **Fine-Tuning**: Verfügbar für GPT-4o-mini und ausgewählte Modelle [Quelle: https://platform.openai.com/docs/guides/fine-tuning]
- **Tool-Use**: Functions/Tools per JSON-Schema. Parallel Calls supported
- **Structured Outputs**: Strikte JSON-Schema-Konformität via `response_format`
- **Prompt Caching**: Automatisches Caching (kein Setup nötig), 90% Rabatt auf GPT-5-Familie
