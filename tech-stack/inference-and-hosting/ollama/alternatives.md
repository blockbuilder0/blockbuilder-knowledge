---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: inference-and-hosting
tech: ollama
---

# Ollama vs. Alternativen

Stand 2026-05-20.

## Wann Ollama wählen

- Entwickler-Setup, schnelle PoCs, Prototyping
- On-Prem-Production mit niedriger bis mittlerer Last (≤ einige zig RPS)
- Apple-Silicon-Hardware (Metal-Beschleunigung sehr gut)
- Heterogene Hardware (NVIDIA + Apple + AMD im selben Team)
- Einheitliche OpenAI-kompatible API für mehrere Modelle
- Embeddings on-prem (nomic-embed-text, bge-m3)

## Wann eine Alternative besser ist

| Anforderung | Bessere Wahl | Begründung |
|---|---|---|
| Hochlast-Production (>100 RPS, viele User parallel) | **vLLM** | PagedAttention, Continuous Batching, deutlich höhere Throughput |
| Multi-GPU mit Tensor-Parallelism | vLLM, TGI, TensorRT-LLM | bessere Multi-Node-/Multi-GPU-Skalierung |
| NVIDIA-only mit max. Performance | TensorRT-LLM | NVIDIA-Stack-optimal |
| Hugging Face-Integration | TGI (Text Generation Inference) | nativ HF |
| Embedded auf Edge-Devices (Mobile/IoT) | `llama.cpp` direkt, MLC LLM | Ollama-Overhead zu groß |
| Reine Closed-Modelle (Claude, GPT-4) | direkte Anbieter-API | Ollama kann das nicht |

## Direktvergleich Inferenz-Runtimes

| Kriterium | Ollama | vLLM | TGI | llama.cpp |
|---|---|---|---|---|
| Lizenz | MIT | Apache 2.0 | Apache 2.0 [Quelle: https://github.com/huggingface/text-generation-inference, abgerufen 2026-05-20] | MIT |
| Setup-Komplexität | sehr gering | mittel | mittel | hoch |
| Throughput (single-GPU, Batch) | mittel | **sehr hoch** | hoch | mittel |
| Apple-Silicon | **ja (Metal)** | nein | nein | ja |
| Modell-Registry | ja | nein (eigene) | HF Hub | nein |
| OpenAI-API | ja | ja | ja | via Wrapper |
| GGUF (quantisiert) | ja | begrenzt | nein | **ja (nativ)** |
| Multi-GPU Tensor-Parallel | begrenzt | **ja** | ja | begrenzt |

## Embeddings: Ollama vs. dedizierte Servers

Für reine Embedding-Workloads ist Ollama OK, aber **Text Embeddings Inference (TEI)** von Hugging Face liefert oft höhere Throughput bei dedizierten Embedding-Pipelines [Quelle: https://github.com/huggingface/text-embeddings-inference].

## Unsere typischen Stacks

- **Default On-Prem-LLM bei Kunden bis ca. 50 RPS** -> Ollama + Mistral Small auf RTX 4090
- **Höhere Last / mehrere parallele Tenants** -> vLLM auf A100/H100
- **BlockBuilder-intern (Embeddings für LightRAG)** -> Ollama mit nomic-embed-text
- **Apple-Silicon Engineer-Laptops** -> Ollama mit Mistral Small / Llama 3.x
