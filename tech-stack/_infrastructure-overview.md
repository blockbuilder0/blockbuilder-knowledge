# Infrastruktur — Hosting, Hardware, Plattformen

Pragmatischer Mix aus EU-Cloud, eigener Hardware und ausgewählten internationalen Diensten — geleitet von Datenresidenz, Kosten und Betriebs­aufwand.

## Bevorzugte Anbieter

### Hetzner (Cloud + Dedicated)
- Deutsche Rechenzentren (Falkenstein, Nürnberg)
- Sehr gutes Preis-Leistungs-Verhältnis
- Konkrete Setups in unseren Projekten:
  - **CPX32** (Shared vCPU x86) für mittelständische SaaS-Apps mit Docker (Beispiel: TipTap-Legal-SaaS)
  - **CAX31** (ARM64) für Personal-Agent-Setups mit niedrigem Energie-Footprint (Beispiel: Real-Estate-Agent)
  - **Storage Box BX11** für Backup (~3,20 EUR/Monat für 1 TB)
- Hetzner ist Default für die meisten Kunden-Deployments im KMU-Segment

### Proxmox (eigener Hypervisor)
- Self-Hosted Virtualisierungs-Plattform
- Geeignet für On-Premise-AI-Setups mit GPU-Passthrough
- Unsere interne LightRAG-Instanz läuft auf Proxmox-VM

### Railway
- Sehr gute DX für TypeScript-/Next.js-Deployments
- Einsatz bei Projekten mit Prio "Time-to-Market" und wenn Datenresidenz nicht hart ist
- Wird auch für die BlockBuilder-Website selbst genutzt

### NVIDIA Hardware
- Default für GPU-Inference (CUDA-Ökosystem)
- RTX 4090 für mittelgroße Modelle in kleinen On-Prem-Setups
- A100 / H100 für hohe Parallelität und große Modelle

### Google TPU
- In Spezialfällen, wenn JAX/TPU-spezifische Modelle relevant sind

## Reverse-Proxy / TLS

| Tool | Sweet Spot |
|---|---|
| **Traefik v3** | Container-Orchestrierung, automatisches Service-Discovery |
| **Caddy** | Einfache Setups mit Let's Encrypt out-of-the-box |
| **nginx** | Wenn schon vorhanden und das Team es kennt |

## DevOps-Stack

- **Docker** + **Docker Compose** für die meisten Single-Host-Deployments
- **Kubernetes** nur, wenn der Kunde es bereits hat (sonst Overkill für Mittelstand)
- **GitHub Actions** für CI/CD
- **Terraform** für Infrastructure-as-Code

## Datenresidenz-Default

| Anforderung | Wahl |
|---|---|
| Maximale Souveränität | Eigene Hardware on-prem (Proxmox + GPU) |
| EU-Compliance ausreichend | Hetzner (DE) |
| Time-to-Market > Datenresidenz | Railway / AWS EU-Region |
| Globale Reichweite | Cloudflare + Multi-Region |

## Was wir explizit NICHT empfehlen

- **US-Cloud als Default für DACH-Mittelstand** — DSGVO-Reibung, FISA-Risiko, oft kein Mehrwert
- **Kubernetes für 3 Services** — Docker Compose reicht und ist wartbar
- **"Multi-Cloud" als Selbstzweck** — Komplexitäts-Multiplikator ohne klaren Use-Case
- **Eigene GPU-Hardware bei < 50 Std/Monat Inference-Last** — Cloud-GPU on-demand billiger

**Verwandt:**
- Self-Hosting: `tech-stack/self-hosting.md`
- On-Premise-Service: `services/on-premise-ai.md`
- Datenresidenz: `compliance/data-residency.md`
