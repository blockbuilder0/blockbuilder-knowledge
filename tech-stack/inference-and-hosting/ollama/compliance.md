---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: inference-and-hosting
tech: ollama
---

# Ollama — Compliance

Stand 2026-05-20.

## DSGVO / GDPR

- **Self-Hosted Runtime** — alle Daten bleiben lokal. Kein Daten-Transfer an Drittanbieter durch Ollama selbst
- **Datenresidenz**: 100% bestimmt durch das Deployment (Laptop, Server, RZ)
- **Modell-Downloads** erfolgen aus der Ollama-Registry (ollama.com) bzw. Hugging Face — das sind reine Modell-Bytes, keine personenbezogenen Daten gehen raus
- **Telemetrie**: Ollama gibt für den lokalen Betrieb explizit an "We don't see your prompts or data"; macOS- und Windows-Clients laden Updates automatisch herunter. Nur die separat aktivierten Cloud-Features erheben "basic account info and limited usage metadata", keine Prompt-Inhalte [Quelle: https://docs.ollama.com/faq, abgerufen 2026-05-20]
- **DPA**: Nicht erforderlich (kein Auftragsverarbeiter)

## EU AI Act

- Ollama ist **Runtime, kein Modell** — die regulatorischen Pflichten zielen auf das verwendete LLM und das Gesamtsystem
- Open-Weights-Modelle (Mistral Apache 2.0, Llama Community License) bringen unterschiedliche Lizenz- und Transparenz-Profile mit. Diese müssen einzeln geprüft werden
- Deployer-Pflichten verbleiben beim Kunden

## Lizenz

- **MIT License** für Ollama-Runtime [Quelle: https://github.com/ollama/ollama/blob/main/LICENSE]
- **Modell-Lizenzen variieren**:
  - Mistral Small / NeMo / Ministral / Pixtral: Apache 2.0 (frei kommerziell)
  - Llama 3.x: Llama Community License (kommerziell mit Einschränkungen über 700M MAU) [Quelle: https://llama.meta.com/llama3/license/]
  - Qwen 2.5 / Qwen 2.5-Coder: Apache 2.0 für 0.5B, 1.5B, 3B, 7B, 14B, 32B [Quelle: https://huggingface.co/Qwen/Qwen2.5-Coder-32B-Instruct, abgerufen 2026-05-20]
  - Codestral: MNPL (Mistral Non-Production License) — kommerzielle Lizenz nötig für Production [Quelle: https://mistral.ai/news/codestral/]

## Sicherheits-Eigenschaften

- HTTP-API standardmäßig nur auf localhost — Exposition über Netzwerk erfordert bewusste Konfiguration
- Kein eingebauter Auth-Mechanismus — Production-Setups brauchen Reverse Proxy mit Auth (Caddy, Traefik, Nginx)
- Modelle können lokal verifiziert werden (Hashes über Manifests)

## Branchen-Eignung

- **Anwaltskanzleien (§ 203 StGB)**: ideal als Runtime für Mistral Small on-prem
- **Behörden**: Open Source + on-prem = vergaberechtlich attraktiv
- **Gesundheit**: on-prem-Setup unkritisch für DSGVO
- **Mittelstand**: niedrigste Einstiegshürde für eigene LLM-Inferenz

## Bezugswege im Vergleich

| Setup | Datenresidenz | Compliance |
|---|---|---|
| Ollama auf Kunden-Server + Mistral Small | beim Kunden | **maximal** |
| Ollama auf Hetzner Dedicated (DE) | EU/DE | sehr hoch |
| Ollama auf Hyperscaler-VM (EU-Region) | EU | hoch |
