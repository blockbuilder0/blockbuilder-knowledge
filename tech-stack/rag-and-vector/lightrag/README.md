---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: rag-and-vector
tech: lightrag
---

# LightRAG

## Was ist das?

LightRAG ist ein Open-Source-RAG-Framework des **HKUDS (Hong Kong University Data Science Lab)**, vorgestellt im Paper "LightRAG: Simple and Fast Retrieval-Augmented Generation" (EMNLP 2025) [Quelle: https://github.com/HKUDS/LightRAG]. Es kombiniert klassische Vektorsuche mit einem **Knowledge Graph** und nutzt **Dual-Level Retrieval** (low-level entity-spezifisch + high-level konzeptuell), um genauere Antworten mit besserer Kontexttiefe zu liefern als reine Vektor-RAG-Systeme.

## Warum wir LightRAG einsetzen

- **Graph + Vektor in einem Stack**: Beziehungen zwischen Entitäten (Personen, Firmen, Verträgen) werden explizit modelliert — bei klassischen Vektorsuchen geht das verloren
- **Dual-Level Retrieval**: Sowohl "Was steht in Vertrag X Paragraf 7?" (low-level) als auch "Wie hängt diese Vertragsart mit unserer DSGVO-Position zusammen?" (high-level) [Quelle: https://github.com/HKUDS/LightRAG]
- **Self-Hostable**: MIT-Lizenz, vollständig on-prem deploybar — kritisch für DSGVO und DACH-B2B
- **Storage-flexibel**: Pluggable Storage-Backends — wir nutzen **PostgreSQL + pgvector**, optional Neo4j, Milvus, Qdrant, MongoDB [Quelle: https://github.com/HKUDS/LightRAG#storage]
- **LLM-agnostisch**: Funktioniert mit OpenAI-kompatiblen APIs, Ollama, Azure OpenAI — wir routen über unseren prAIvicy-Gateway
- **WebUI inklusive**: Graph-Visualisierung, Dokument-Upload, Query-Interface out of the box

## Wie wir LightRAG integrieren

Produktiv im Einsatz für BlockBuilder selbst:
- **Deployment**: Docker-Container auf Proxmox-VM `192.168.2.100`, Port `9621` [interner Stack]
- **Storage**: PostgreSQL 16 mit pgvector-Extension
- **Embeddings**: Ollama `nomic-embed-text` (768 Dim, lokal, kostenlos)
- **LLM**: MiniMax M2.7 via prAIvicy Gateway
- **Indexiert**: ca. 440 Geschäftsdokumente (Rechnungen, Belege, Verträge, Korrespondenz), ca. 7640 Entities
- **Zugriff**: Skill `/lightrag` (Suche), `/lightrag-index` (neue Dokumente), WebUI via VPN
- **Kundenprojekte**: Gleicher Stack als Blaupause für DACH-Kunden mit Knowledge-Mgmt-Bedarf

## Wofür eignet sich LightRAG NICHT?

- **Echtzeit-Indexierung mit sub-Sekunden-Latenz**: Indexierung ist LLM-gestützt (Entity-Extraktion) und damit teuer — Batch-Updates eignen sich besser
- **Sehr große Korpora (>10 Mio Dokumente)**: Graph-Aufbau wird teuer; hier eher Hybrid mit dediziertem Search-Stack (OpenSearch, Vespa)
- **Strukturierte SQL-Daten**: Kein Ersatz für Text-to-SQL oder klassische BI
- **Multimodale Inhalte (Bilder/Video)**: Fokus liegt auf Text; Vision-Support ist limitiert
- **No-Code-Setup für Endkunden**: Setup und Tuning brauchen Engineering-Zeit
