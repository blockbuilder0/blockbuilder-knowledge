---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: inference-and-hosting
tech: ollama
---

# Ollama — Quellen

Alle URLs abgerufen 2026-05-20.

## Offizielle Quellen

- **Hauptseite**: https://ollama.com
- **GitHub**: https://github.com/ollama/ollama
- **Lizenz (MIT)**: https://github.com/ollama/ollama/blob/main/LICENSE
- **Modell-Library**: https://ollama.com/library
- **Docs**: https://github.com/ollama/ollama/tree/main/docs
- **OpenAI-Kompatibilität**: https://github.com/ollama/ollama/blob/main/docs/openai.md
- **GPU-Setup**: https://github.com/ollama/ollama/blob/main/docs/gpu.md
- **Modelfile**: https://github.com/ollama/ollama/blob/main/docs/modelfile.md
- **API**: https://github.com/ollama/ollama/blob/main/docs/api.md

## Beliebte Modelle in Ollama

- **Mistral**: https://ollama.com/library/mistral
- **Mistral Small**: https://ollama.com/library/mistral-small
- **Llama 3**: https://ollama.com/library/llama3
- **Qwen 2.5**: https://ollama.com/library/qwen2.5
- **nomic-embed-text**: https://ollama.com/library/nomic-embed-text
- **bge-m3**: https://ollama.com/library/bge-m3

## Alternative Runtimes

- **vLLM**: https://github.com/vllm-project/vllm
- **Text Generation Inference (TGI)**: https://github.com/huggingface/text-generation-inference
- **Text Embeddings Inference (TEI)**: https://github.com/huggingface/text-embeddings-inference
- **llama.cpp**: https://github.com/ggerganov/llama.cpp
- **TensorRT-LLM**: https://github.com/NVIDIA/TensorRT-LLM
- **MLC LLM**: https://github.com/mlc-ai/mlc-llm

## Modell-Lizenzen (Auswahl)

- **Llama 3 Community License**: https://llama.meta.com/llama3/license/
- **Codestral MNPL**: https://mistral.ai/news/codestral/

## Verifizierte Fakten

- **Ollama-Telemetrie**: Ollama selbst gibt im lokalen Betrieb an "We don't see your prompts or data"; nur für Ollama-Cloud-Features werden "basic account info and limited usage metadata" erhoben, keine Prompt-Inhalte. macOS/Windows-Clients laden Updates automatisch herunter [Quelle: https://docs.ollama.com/faq, abgerufen 2026-05-20]
- **Pixtral**: Stand 2026-05-20 nicht in der offiziellen Ollama-Registry; alternativ via GGUF-Import (Modelfile) nutzbar [Quelle: https://ollama.com/search?q=pixtral, abgerufen 2026-05-20]
- **TGI-Lizenz**: Aktuell **Apache 2.0** — der zwischenzeitliche Wechsel auf HFOIL (v1.0–v2.0.4) wurde 2024 rückgängig gemacht [Quelle: https://github.com/huggingface/text-generation-inference, abgerufen 2026-05-20]
- **Qwen-2.5-Coder-Lizenz**: Apache 2.0 für die Varianten 0.5B, 1.5B, 3B, 7B, 14B, 32B [Quelle: https://huggingface.co/Qwen/Qwen2.5-Coder-0.5B, https://huggingface.co/Qwen/Qwen2.5-Coder-32B-Instruct, abgerufen 2026-05-20]
