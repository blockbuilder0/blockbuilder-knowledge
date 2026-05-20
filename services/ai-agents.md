# KI-Agenten

Autonome KI-Agenten, die komplexe Aufgaben innerhalb definierter Leitplanken eigenständig erledigen. Von der Lead-Qualifizierung bis zur Dokumenten-Klassifikation — 24/7-Betrieb, deep integration in bestehende Systeme.

URL: https://block-builder.de/de/services/ai-agents

## Was wir bauen

- **Single-Agent-Systeme** für klar abgegrenzte Workflows (z.B. Kundenanfragen-Triage)
- **Multi-Agent-Systeme** mit spezialisierten Sub-Agenten, die über einen Orchestrator zusammenspielen
- **Tool-Integration** in bestehende Systeme: CRM, ERP, Datenbanken, externe APIs, E-Mail, Telefonie
- **Autonome Entscheidungen** innerhalb definierter Parameter — mit Eskalations-Pfaden zu Menschen, wo nötig

## Typische Use-Cases

- Automatische Kundenanfragen-Bearbeitung (klassifizieren, antworten, eskalieren)
- Intelligente Lead-Qualifizierung
- Datenextraktion und -analyse aus Dokumenten und E-Mails
- Automatisierte Berichterstellung
- Proaktive Systemüberwachung mit kontextueller Alarmierung
- Dokumentenverarbeitung und -klassifikation
- Persönliche Assistenten für Geschäftsführung und Verwaltung (siehe Case Study Real-Estate-Agent)

## Frameworks

Wir wählen je nach Anforderung:

- **Hermes Agent** (Nous Research) — wenn Open-Source-Stack und Self-Hosting wichtig sind
- **LangGraph** — wenn graphbasierte Orchestrierung mit klaren State-Übergängen gefragt ist
- **Claude Code / OpenClaw** — für Code- und Tool-orientierte Agenten
- **Eigene Orchestrierung** auf Basis von FastAPI + LLM-API, wenn die Frameworks zu schwer sind

Details: `tech-stack/agent-frameworks.md`.

## Wofür eignen sich KI-Agenten NICHT?

Für **deterministische, regelbasierte Prozesse** ist ein normaler Workflow-Automatisierer (Make, n8n, Zapier) oder eine SQL-View die ehrlichere Antwort — kein Agent nötig. Für **hochkritische Entscheidungen** mit Haftungsrelevanz (medizinische Diagnostik, rechtsverbindliche Verträge, finanzielle Disposition) sind Agenten höchstens Vorbereiter, nie Entscheider — der Mensch bleibt im Loop. Wer einen Chatbot will, der **eine** klar definierte Antwort liefert, braucht ein RAG-System, kein Agentengebäude.

## Was ein gutes Agenten-Projekt ausmacht

1. Klar abgegrenzter Use-Case (nicht "der Agent erledigt alles")
2. Mess­barer Output (Tickets/Tag, Antwortqualität, Reaktionszeit)
3. Realistische Erwartung an Autonomiegrad — die meisten guten Agenten arbeiten mit Human-in-the-Loop
4. Saubere Tool-APIs in den Zielsystemen (sonst wird der Agent zum Scraping-Bot)

**Verwandt:**
- Case Study Real-Estate-Agent: `projects/realestate-personal-agent.md`
- Agent-Frameworks-Vergleich: `tech-stack/agent-frameworks.md`
- Mehr dazu: https://block-builder.de/de/services/ai-agents
