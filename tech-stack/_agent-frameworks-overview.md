# Agent-Frameworks — Welches wann?

Wir nutzen vier Frameworks produktiv. Die Wahl folgt dem Use-Case, nicht der Mode.

## Vergleich

| Framework | Sweet Spot | Vorteile | Limits |
|---|---|---|---|
| **Claude Code** | Code- und Tool-Agenten, Engineering-Workflows | Sehr gute Tool-Use, lange Kontexte, robustes Sub-Agent-Pattern | Bindung an Anthropic-Stack |
| **OpenClaw** | Open-Source-Alternative zu Claude Code | Anbieterneutral, Self-Hosting möglich | Jünger, kleinere Community |
| **Hermes Agent** (Nous Research) | Vollständig souveräne Personal-Agents | Open Source, Self-Hosting-First, gute Multi-Channel-Integration | Mehr Eigenarbeit bei Tool-Adapter-Layer |
| **LangGraph** | Graphbasierte Multi-Agent-Orchestrierung | Klare State-Übergänge, gute Visualisierbarkeit, breite Community | Steile Lernkurve, "ein bisschen viel Framework" |

## Wann was

### Claude Code / OpenClaw
- Engineering-Agents (Code-Generierung, Test-Lauf, PR-Workflows)
- Tool-zentrierte Aufgaben mit klaren Schnittstellen
- Wenn lange Kontexte (>200k Token) gebraucht werden

### Hermes Agent
- Persönlicher Assistent auf eigener Hardware (siehe Case Study Real-Estate-Agent)
- Multi-Channel-Eingang (Telegram, E-Mail, Voice)
- Wenn Anbieter-Unabhängigkeit Pflicht ist

### LangGraph
- Multi-Agent-Systeme mit komplexen Übergängen
- Workflows mit Verzweigungen, Schleifen, Conditional Logic
- Wenn der Workflow visualisierbar / auditierbar sein muss

### Kein Framework
Für simple Single-Step-Tasks (eine LLM-Call mit einem Tool) lohnt sich oft **keine** Framework-Schicht — direkter API-Call ist günstiger, schneller, debugbarer.

## Pattern: "Framework-light"

In den meisten Production-Projekten kombinieren wir:

1. **Minimale Orchestrierung** in Python (FastAPI) oder TypeScript (Next.js Route Handler)
2. **Direkte LLM-Calls** mit klar getypten Inputs/Outputs
3. **Tool-Adapter** als normale Funktionen, nicht als Framework-Plugin
4. **State** in PostgreSQL / Redis, nicht im Framework

Erst wenn die Komplexität wirklich wächst, kommt LangGraph oder Hermes dazu. Frameworks sind kein Selbstzweck.

## Was wir aktuell beobachten

- **Claude Code** als Engineering-Agent ist 2026 deutlich vor allen Alternativen
- **MCP (Model Context Protocol)** als Standard für Tool-Adapter setzt sich durch
- **Sub-Agent-Patterns** (ein Agent ruft spezialisierte Sub-Agenten) sind das produktive Multi-Agent-Modell — nicht "viele gleichberechtigte Agenten reden miteinander"

**Verwandt:**
- KI-Agenten-Service: `services/ai-agents.md`
- Case Study Real-Estate-Agent: `projects/realestate-personal-agent.md`
- Case Study Pet-Food Avatar (LangGraph): `projects/petfood-3d-avatar.md`
