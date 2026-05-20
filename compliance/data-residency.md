# Datenresidenz — On-Premise, EU-Cloud, Global

Drei Modelle, klare Entscheidungs­kriterien. Wir empfehlen nicht pauschal, sondern abhängig vom Use-Case.

## On-Premise (kundeneigene Hardware)

**Wann sinnvoll:**
- Daten dürfen das Gebäude nicht verlassen (Verteidigung, Gesundheits­daten der höchsten Schutz­klasse, Geschäfts­geheimnisse mit existenziellem Wert)
- Hohe Inference-Last (Break-Even gegenüber Cloud-API typischerweise nach 12–24 Monaten)
- Vorhandene IT-Infrastruktur und Ops-Team
- Langfristige Nutzung (3+ Jahre)

**Praktisch:**
- NVIDIA-GPU-Server, Investitions­schwelle ~15.000 EUR (Einstieg)
- ~300 EUR/Monat laufend (Strom, Wartung)
- Proxmox oder Docker als Hypervisor/Container-Layer
- vLLM für Production-Inference

## EU-Cloud (dediziert, DE/AT)

**Wann sinnvoll:**
- DSGVO ist wichtig, aber Daten dürfen EU-Rechenzentrum erreichen
- Kein eigenes IT-Team
- Schneller Start gewünscht (3–7 Tage)
- Flexibilität wichtiger als Ein­malig­kosten

**Praktisch:**
- Hetzner (Falkenstein, Nürnberg)
- IONOS, OVH (für Spezialfälle)
- AWS / Azure / GCP **EU-Region** mit DPA und SCC (US-Anbieter-Risiko bewusst akzeptiert)
- Monatliche Miete dedizierter Instanz ab ~499 EUR

## Global Cloud (US-Anbieter, EU-Region OK)

**Wann sinnvoll:**
- Time-to-Market ist Top-Priorität
- Use-Case erlaubt DPA-basierte Compliance (kein hochsensibles Daten­material)
- Daten sind ohnehin schon im US-Ökosystem (Microsoft 365, Google Workspace etc.)
- Kunde hat bewusste Risiko­abwägung getroffen

**Praktisch:**
- AWS / Azure / GCP **EU-Region** + DPA + SCC
- Cloudflare für Edge-Caching
- OpenAI / Anthropic Cloud-APIs mit EU-Routing wo verfügbar

## Hybrid (häufiges Realmuster)

In der Praxis kombinieren viele KMU:

1. **Frontend / Webhosting**: Global Cloud (z.B. Railway, Vercel) — keine sensiblen Daten
2. **App-Backend**: EU-Cloud (Hetzner DE)
3. **AI-Inference**: On-Premise oder dedizierte EU-Instanz
4. **Backup**: EU-Storage (Hetzner Storage Box, BorgBackup verschlüsselt)

Das ist oft die ehrlichste Antwort: man muss nicht alles auf einer Achse maximal souverän halten.

## Entscheidungs­matrix in 4 Fragen

1. **Verlangt der Use-Case Daten­export außerhalb EU?** Wenn nein → mind. EU-Cloud.
2. **Sind die Daten existenz­kritisch oder unter besonderem gesetzlichem Schutz?** Wenn ja → On-Premise oder dedizierte EU-Instanz.
3. **Ist das Inference-Volumen so hoch, dass APIs teurer werden als eigene GPUs?** Wenn ja → On-Premise prüfen.
4. **Hat das Unter­nehmen ein IT-Team und langfristige Perspektive?** Wenn nein → EU-Cloud-Hosted.

## Was wir explizit NICHT empfehlen

- **"Alles on-premise" aus Prinzip** — Kosten und Operations-Last unterschätzt
- **US-Default für DACH-KMU** — DSGVO-Reibung und FISA-Risiko ohne Mehrwert
- **Multi-Cloud-Komplexität ohne Use-Case** — Multiplikator ohne Resilienz-Gewinn

**Verwandt:**
- DSGVO: `compliance/dsgvo-positioning.md`
- On-Premise-Service: `services/on-premise-ai.md`
- Infrastruktur: `tech-stack/infrastructure.md`
- Entscheidung On-Prem vs Cloud: `decision-matrices/on-premise-vs-cloud-ai.md`
