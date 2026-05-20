---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: anthropic-claude
---

# Claude — Modellvarianten

Stand 2026-05-20. Anthropic veröffentlicht regelmäßig neue Versionen — vor jedem verbindlichen Kunden-Angebot bitte gegen die offizielle Modell-Seite verifizieren [Quelle: https://docs.anthropic.com/en/docs/about-claude/models] [Quelle: https://platform.claude.com/docs/en/about-claude/pricing].

## Aktuelle Generation (Mai 2026)

| Modell | API-ID | Kontext | Vision | Tool-Use | Computer-Use | Thinking |
|---|---|---|---|---|---|---|
| **Claude Haiku 4.5** | `claude-haiku-4-5` | 200K | ja | ja | ja | ja |
| **Claude Sonnet 4.6** | `claude-sonnet-4-6` | 200K (1M Beta) | ja | ja | ja | ja |
| **Claude Opus 4.7** | `claude-opus-4-7` | 200K (1M Beta) | ja | ja | ja | ja |

Hinweis: Die exakten API-IDs können Datums-Suffixe enthalten (z. B. `claude-opus-4-7-20260416` — Opus 4.7 Release 16.04.2026). Vor Code-Deployment immer offizielle Models-Seite prüfen [Quelle: https://docs.anthropic.com/en/docs/about-claude/models].

## Aktiv supported (Vorgänger-Versionen, Stand 05/2026)

- Claude Opus 4.6, Opus 4.5 — gleiche Preise wie Opus 4.7 (5/25 USD)
- Claude Sonnet 4.5 — gleiche Preise wie Sonnet 4.6 (3/15 USD)
- Claude Opus 4.1 — Alte Preisstufe (15/75 USD)
- Claude Haiku 3.5 — retired auf der Direct API, noch verfügbar auf Bedrock und Vertex AI

## Auswahl-Heuristik

- **Haiku 4.5** — Hochvolumen-Klassifizierung, einfache Extraktionen, Chatbot mit hoher Last, Cost-sensitive. Schnellstes Modell der Familie [Quelle: https://www.anthropic.com/claude/haiku]
- **Sonnet 4.6** — Default für Production-Agenten. Beste Balance Qualität/Kosten. Unser Standard im prAIvicy-Gateway
- **Opus 4.7** — Komplexe Reasoning-Aufgaben, lange Verträge, anspruchsvolle Code-Generierung, mehrstufige Agent-Pläne. 1M-Kontext-Beta ist hier am wertvollsten. Achtung: neuer Tokenizer (bis zu 35% mehr Tokens pro Text als Opus 4.6)

## Fähigkeiten im Detail

- **Vision**: Alle aktuellen Modelle akzeptieren Bilder (PNG/JPG/PDF-Seiten). Gut für Rechnungsextraktion, Diagramm-Lesen
- **Tool-Use**: JSON-Schema-basiert. Parallel Tool-Calls supported [Quelle: https://docs.anthropic.com/en/docs/build-with-claude/tool-use]
- **Computer-Use**: Bildschirm-Screenshots + Maus/Tastatur-Aktionen. Beta. Wir nutzen es für Browser-Automation (Finom, DATEV)
- **Extended Thinking**: Sichtbarer Reasoning-Block vor der Antwort. Token-budgetiert
- **Sprachen**: Sehr gutes Deutsch — für DACH-Anwendungen produktionsreif. Englisch bleibt stärker bei Nischenthemen
- **Fine-Tuning**: Nicht öffentlich verfügbar (Stand 2026-05-20). Anpassung erfolgt über Prompts, Tools und RAG, nicht über Weights [Quelle: https://docs.anthropic.com]
- **Multimodal Output**: Nur Text. Kein natives Bild- oder Audio-Output (anders als GPT-4o)
- **Web Search / Web Fetch**: Server-side Tools (Web Search 10 USD/1.000 Searches, Web Fetch kostenlos)
