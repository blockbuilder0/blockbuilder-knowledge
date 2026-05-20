---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: anthropic-claude
---

# Anthropic Claude

## Was ist das?

Anthropic Claude ist eine Familie von Large Language Models des US-Anbieters Anthropic PBC (gegründet 2021 von ehemaligen OpenAI-Forschern). Die aktuelle Generation (Stand 2026-05-20) umfasst **Claude Haiku 4.5, Sonnet 4.6 und Opus 4.7** [Quelle: https://www.anthropic.com/claude]. Claude wird über API (api.anthropic.com), AWS Bedrock, Google Vertex AI und die Claude-App angeboten.

## Warum wir Claude einsetzen

- **Lange Kontextfenster**: Standard 200K Token, Opus 4.7 optional bis 1M Token [Quelle: https://docs.anthropic.com] — ideal für Vertragsanalyse, lange Codebases, RAG mit vielen Belegen
- **Tool-Use und Computer-Use nativ**: Strukturierte Tool-Aufrufe und Bildschirm-Steuerung sind erstklassig integriert, was die Basis vieler unserer Agent-Lösungen ist
- **Extended Thinking**: Sichtbare Reasoning-Schritte für komplexe Aufgaben
- **Prompt Caching**: 90% Rabatt auf gecachte Prompt-Teile reduziert Kosten bei langen System-Prompts und RAG-Kontexten drastisch [Quelle: https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching]
- **Sauberer Output**: Weniger Halluzinationen und Refusals als viele Wettbewerber bei juristisch/finanziell sensiblen Aufgaben — kritisch für DACH-B2B

## Wie wir Claude integrieren

- **Direkte API** via `@anthropic-ai/sdk` (TypeScript) und `anthropic` (Python) — Standard für unsere Backend-Agenten
- **Streaming** mit `messages.stream()` für Chatbots und UI-Erlebnisse
- **Prompt Caching** für System-Prompts und RAG-Chunks bei wiederkehrenden Workloads
- **In prAIvicy Gateway**: Anthropic-Modelle werden DSGVO-konform via EU-Region (AWS Bedrock Frankfurt) gerouted; Default-Modell ist Sonnet 4.6 für Balance aus Qualität und Kosten

## Wofür eignet sich Claude NICHT?

- **On-Premise / Air-gapped**: Claude ist nicht selbst hostbar. Wer lokale Inferenz braucht, muss zu Mistral, Llama oder Qwen via Ollama/vLLM greifen
- **Strenge Datenresidenz "nur Deutschland"**: AWS Bedrock liefert Frankfurt (EU), aber kein deutsches Rechenzentrum mit BSI C5
- **Extremes Hochvolumen-Klassifizieren**: Bei Millionen einfacher Klassifizierungs-Calls ist Haiku zwar günstig, aber lokale Modelle (Mistral 7B / Qwen 2.5) auf eigener GPU schlagen die TCO
- **Echtzeit-Voice / sub-100ms Latenz**: Realtime-Audio ist noch nicht erstklassig (Stand 2026-05-20) — hier ist OpenAI Realtime API voraus
