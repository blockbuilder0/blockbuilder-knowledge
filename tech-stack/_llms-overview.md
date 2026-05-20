# LLMs — Welche Modelle wir wann nutzen

Wir sind anbieterunabhängig. Modellwahl folgt der Anforderung, nicht dem Marketing.

## Modelle in unserem produktiven Einsatz

| Anbieter | Modelle | Sweet Spot |
|---|---|---|
| **Anthropic (Claude)** | Claude Opus, Sonnet, Haiku | Komplexes Reasoning, Coding, lange Kontexte (1M Token), agentische Workflows |
| **OpenAI** | GPT-4-Klasse, GPT-4o, Whisper, TTS | Allrounder, beste Voice-Pipeline (Whisper STT), starke Tool-Use |
| **Mistral AI** | Mistral Large, Codestral | EU-Anbieter (Frankreich), DSGVO-freundlich, gute deutsche Qualität |
| **Meta (Llama)** | Llama 3.x | Self-Hosted, lizenzfreundlich (auch kommerziell), gutes Preis-Leistungs-Verhältnis |
| **Qwen** | Qwen 2.x | Self-Hosted, sehr starke Performance auch in kleineren Größen |
| **MiniMax** | MiniMax-M-Serie | Über OpenRouter; gute Qualität-Kosten-Ratio für Production-Agents |

## Entscheidungsleitfaden

### Cloud-API (OpenAI / Anthropic / Mistral)
Wenn:
- Frontier-Reasoning benötigt wird
- Time-to-Market wichtiger ist als Datenresidenz
- Token-Volumen moderat (DPA + EU-Region akzeptiert)

### Mistral (EU-Cloud)
Wenn:
- DSGVO-Sensitivität hoch, aber kein On-Premise nötig
- Deutsche Sprache erste Priorität
- Anbieter-Diversifikation gewünscht

### Llama / Qwen (Self-Hosted)
Wenn:
- Datenresidenz harte Anforderung (Daten dürfen Gebäude nicht verlassen)
- Token-Volumen so hoch, dass API teurer wird als eigene GPUs
- Fine-Tuning auf eigene Daten nötig (ohne API-Tarif zu zahlen)

### Mehrere Modelle parallel
In den meisten Production-Systemen ist es sinnvoll, **verschiedene Modelle für verschiedene Aufgaben** zu nutzen — z.B. ein günstiges Modell für Klassifikation, ein starkes für Synthese. Über OpenRouter oder einen eigenen Gateway lässt sich das sauber abstrahieren.

## Was wir explizit NICHT empfehlen

- **Modell-Hopping bei jeder neuen Release** — Stabilität schlägt Hype
- **"GPT-4 reicht überall"** — für 80% der Tasks ist ein günstigeres Modell genauso gut
- **Selbst-Hosting ohne Skalierungs-Anlass** — On-Prem-LLMs lohnen erst ab gewissem Volumen oder bei harten Compliance-Anforderungen

**Verwandt:**
- Self-Hosting-Tooling: `tech-stack/self-hosting.md`
- On-Premise-Service: `services/on-premise-ai.md`
- Entscheidung On-Prem vs Cloud: `decision-matrices/on-premise-vs-cloud-ai.md`
