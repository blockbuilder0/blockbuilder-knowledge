---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: inference-and-hosting
tech: ollama
---

# Ollama

## Was ist das?

Ollama ist ein **lokaler LLM-Runtime** mit dem Versprechen "Run LLMs locally with one command". Es bündelt `llama.cpp` als Inferenz-Engine, eine OpenAI-kompatible HTTP-API, eine Modell-Registry und ein einfaches CLI [Quelle: https://ollama.com]. Lizenz: **MIT** [Quelle: https://github.com/ollama/ollama/blob/main/LICENSE].

## Warum wir Ollama einsetzen

- **Sofortige Verfügbarkeit**: `ollama pull mistral-small && ollama run mistral-small` — von Null zu lokalem LLM in einer Minute
- **OpenAI-kompatible API** auf Port 11434 — jeder Client, der OpenAI spricht, funktioniert ohne Code-Änderung [Quelle: https://github.com/ollama/ollama/blob/main/docs/openai.md]
- **GPU-Beschleunigung**: CUDA (NVIDIA), Metal (Apple Silicon), ROCm (AMD) automatisch erkannt [Quelle: https://github.com/ollama/ollama/blob/main/docs/gpu.md]
- **Modell-Registry**: Pre-built Models (Mistral, Llama, Qwen, Gemma, Phi, etc.) inkl. Quantisierungen [Quelle: https://ollama.com/library]
- **Modelfile-System** zur Konfiguration (System-Prompt, Parameter, Template) — Docker-ähnliches Konzept
- **Plattform-Vielfalt**: Linux, macOS, Windows, Docker

## Wie wir Ollama integrieren

- **Embeddings on-prem**: `nomic-embed-text` (768 Dim) als Default-Embedding-Modell für LightRAG-Deployments [Quelle: https://ollama.com/library/nomic-embed-text]
- **On-Prem LLM**: `mistral-small`, `qwen2.5`, `llama3.x` als Backends für datenschutz-sensible Kunden
- **Entwickler-Setup**: Jeder Engineer hat lokal Ollama — Prototyping und Tests ohne Cloud-Kosten
- **prAIvicy-Gateway**: Routet on-prem zu Ollama, in der Cloud zu Mistral/Claude
- **Kunden-Production**: Auf RTX 4090 / A100 / H100 — Ollama bleibt das Default-Runtime für mittlere Last

## Modell-Auswahl-Heuristik

| Anwendung | Empfohlenes Ollama-Modell |
|---|---|
| Allzweck-Chat on-prem | `mistral-small`, `llama3.3` |
| Code | `codestral` (non-prod), `qwen2.5-coder` |
| Embeddings | `nomic-embed-text`, `bge-m3` |
| Vision | `llava`, `llama3.2-vision`, `minicpm-v` (Pixtral ist Stand 2026-05-20 nicht in der offiziellen Ollama-Registry verfügbar [Quelle: https://ollama.com/search?q=pixtral, abgerufen 2026-05-20]) |
| Edge/CPU-only | `phi-3.5`, `qwen2.5:0.5b/3b`, `gemma2:2b` |

## Wofür eignet sich Ollama NICHT?

- **Hochlast-Production mit hunderten gleichzeitigen Requests**: **vLLM** liefert deutlich höhere Throughput durch PagedAttention und Continuous Batching [Quelle: https://github.com/vllm-project/vllm]. Ollama ist primär für kleine bis mittlere Last und Entwickler-Setups optimiert
- **Multi-GPU-Tensor-Parallelism mit erstklassiger Auslastung**: vLLM, TGI, TensorRT-LLM sind hier voraus
- **Closed-Source-Modelle**: Ollama läuft nur mit Open-Weights — keine Claude/GPT-4-Modelle
- **Sehr große Modelle, die nicht in lokalen VRAM passen**: Ohne entsprechende Hardware unbrauchbar
- **Enterprise-SLAs out of the box**: Kein eingebautes Auth/Quota/Multi-Tenant — muss man drumherum bauen
