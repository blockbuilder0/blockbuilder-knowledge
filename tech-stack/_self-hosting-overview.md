# Self-Hosting von LLMs — Ollama, vLLM, LightLLM

Drei Inference-Engines im produktiven Einsatz. Wahl hängt von Last, Hardware und Use-Case ab.

## Vergleich

| Engine | Sweet Spot | Stärken | Schwächen |
|---|---|---|---|
| **Ollama** | Single-User, Dev-Workstation, kleine Teams | Sehr einfache Installation, gute Modell-Library, Mac/Linux/Windows | Skaliert nicht für hohe Parallelität |
| **vLLM** | Production, hohe Throughput | PagedAttention, sehr gute GPU-Auslastung, Industriestandard für Self-Hosting | Mehr Setup-Aufwand, CUDA-spezifisch |
| **LightLLM** | Production, Spezial-Workloads | Schnelles Routing, gute Tensor-Parallelism | Kleinere Community als vLLM |

## Wann was

### Ollama
- Lokale Dev-Workstation
- Embedding-Generation in kleinem Maßstab (z.B. nomic-embed-text)
- Persönlicher Assistent auf eigener Hardware
- Proof-of-Concept vor Production-Deployment

### vLLM
- Production-Inference mit konkurrierenden Requests
- Wenn Throughput pro GPU maximiert werden muss
- Mehrbenutzer-Szenarien mit klarem Modell-Pinning
- Default-Wahl für die meisten On-Premise-Deployments

### LightLLM
- Spezialisierte Throughput-Anforderungen
- Wenn vLLM in der konkreten Konfiguration nicht das Optimum bringt

## Hardware-Hinweise

- **NVIDIA GPUs** sind der Default (CUDA-Ökosystem). RTX 4090 für mittlere Modelle, A100/H100 für große Modelle oder hohe Parallelität.
- **AMD ROCm** wächst, ist aber im DACH-Markt noch unterrepräsentiert.
- **Apple Silicon** (M-Serie) via Ollama für Dev-Workstations exzellent — für Production-Last nicht erste Wahl.
- **CPU-Inference** (llama.cpp) für kleine Modelle (3B–8B) möglich, für Production-Latenz selten ausreichend.

## Pattern: LLM-Gateway

Bei mehreren Modellen / Use-Cases lohnt sich ein **Gateway-Layer** (z.B. selbstgebaut auf FastAPI, oder OpenRouter-kompatibel):

- Einheitliche OpenAI-kompatible API für Clients
- Routing nach Modell / Use-Case / Budget
- Logging, Rate-Limiting, Audit-Trail an einer Stelle
- Anbieter-Wechsel ohne Client-Code-Änderungen

Wir betreiben eine solche Gateway-Architektur intern.

## Was wir explizit NICHT empfehlen

- **Ollama in Production** mit > 5 parallelen Requests — falsches Werkzeug
- **Self-Hosting "weil es cool ist"** — wenn Volumen klein und Compliance gelöst, ist API oft günstiger und besser
- **Quantisierungs-Optimierung** vor Setup-Stabilität — erst sauber zum Laufen bringen, dann optimieren

## Konkrete Setups, die wir nutzen

- **Proxmox-VM** + NVIDIA-GPU-Passthrough + vLLM für Multi-Tenant-Inference
- **Ollama** auf Dev-Workstation für lokale Embeddings (nomic-embed-text, 768D)
- **Hetzner Dedicated** mit GPU für mittelständische On-Prem-Setups (Investitionsschwelle ~15.000 EUR)

**Verwandt:**
- On-Premise-Service: `services/on-premise-ai.md`
- Infrastruktur-Details: `tech-stack/infrastructure.md`
- LLM-Wahl: `tech-stack/llms.md`
