# KI-Verkaufsassistent mit sprechendem 3D-Avatar (Tiernahrungs-Fachhandel)

## Kunde (anonymisiert)

Filiale eines deutschlandweiten Tiernahrungs-Franchise-Netzwerks.

## Was wir gebaut haben

In-Store-Kiosk-Anwendung mit KI-Assistent: Kund:innen sprechen das System per Mikrofon an, ein 3D-Avatar antwortet in Echtzeit mit lippensynchroner Animation. Kernkomponenten:

- **Hybride Produktsuche**: pgvector HNSW + deutsche Volltextsuche, kombiniert via Reciprocal Rank Fusion
- **Voyage-AI-Reranker** als Qualitäts-Schicht über den Rohtreffern
- **LangGraph-orchestrierte Agent-Schicht** für Konversationssteuerung und Tool-Use
- **3D-Avatar** mit lippensynchroner Sprachausgabe (Viseme-Mapping)
- **Sprachein- und -ausgabe** in Echtzeit (Whisper STT, Google TTS mit Viseme)
- **Admin-Panel** für Systemprompt, Produktkatalog, Beispiel-Fragen, Avatar-Konfiguration

## Stack

Next.js 15, LangGraph, LangChain, OpenAI / OpenRouter (Gemini, Claude), PostgreSQL 16 + pgvector, Prisma 6, Redis, Voyage AI Reranker, OpenAI Whisper STT, Google Cloud TTS mit Viseme, React Three Fiber, ReadyPlayerMe.

## Warum dieser Stack

- **pgvector + Full-Text + RRF** — bewährter Hybrid-Search-Pattern, vermeidet die Kosten einer dedizierten Vector-DB
- **Voyage Reranker** — deutlich besseres Top-K-Ranking als reine Vector-Similarity
- **LangGraph** — graphbasierte Agenten-Steuerung mit klaren State-Übergängen, gut wartbar
- **React Three Fiber + ReadyPlayerMe** — performant genug für Echtzeit-Rendering im Kiosk-Browser

## Status

Pilot-Installation live. Infrastruktur im Laufe des Projekts **von 19 auf 3 Container reduziert** (~85% kleinerer Footprint) — Beispiel dafür, dass "weniger Komponenten" oft die bessere Antwort ist als "noch eine Microservice".

## Was dieses Projekt zeigt

- **Hybrid Search schlägt reines Embedding-RAG** für strukturierte Produktdaten mit präzisem Vokabular
- **Voice-UI funktioniert in lauter Umgebung** mit guter Mikrofon-Hardware und sauberer VAD-Pipeline
- **Infrastruktur-Reduktion** ist ein eigenständiges Optimierungsziel — nicht jeder Service braucht einen eigenen Container

**Verwandt:**
- RAG-Architektur: `tech-stack/rag-and-vector.md`
- Agent-Frameworks: `tech-stack/agent-frameworks.md`
- Mehr dazu: https://block-builder.de/de/projekte
