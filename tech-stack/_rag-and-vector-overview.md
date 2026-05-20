# RAG & Vector Search — Welches Tool wann?

Wir nutzen drei Hauptansätze produktiv: LightRAG, pgvector und Qdrant. Die Wahl hängt von Datenvolumen, Query-Pattern und Betrieb ab.

## Übersicht

| Tool | Sweet Spot | Stärken | Schwächen |
|---|---|---|---|
| **LightRAG** (HKUDS) | Graph-RAG über strukturierte Korpora (Verträge, Dokumentation) | Knowledge-Graph + Vector kombiniert, sehr gut für Q&A über Dokumentensammlungen | Junges Projekt, mehr Setup-Aufwand |
| **pgvector** | Embeddings in bestehender PostgreSQL | Keine extra DB, transaktional, HNSW-Index gut genug für die meisten Use-Cases | Skaliert irgendwann nicht mit dedizierten Vector-DBs mit |
| **Qdrant** | Dedizierte Vector-DB für hohes Volumen | Sehr gute Performance, ausgereifte Filter-Operatoren, gute Skalierung | Eigener Betrieb, eigene Backup-Strategie |

Außerdem regelmäßig im Einsatz: **Hugging Face** Hub für Embeddings-Modelle und Modell-Vergleich.

## Entscheidungsleitfaden

### pgvector wählen wenn:
- PostgreSQL ist bereits da
- Volumen < 10 Mio. Embeddings (mit HNSW-Index)
- Transaktionalität wichtig (Embeddings müssen mit Geschäftsdaten konsistent sein)
- Operations-Team will keine zweite Datenbank betreiben

### Qdrant wählen wenn:
- Vector-Volumen > 10 Mio. Embeddings
- Komplexe Metadaten-Filter performant sein müssen
- Hot-Reload-Updates ohne PG-Lock-Probleme nötig
- Eigene K8s-Infrastruktur sowieso vorhanden

### LightRAG wählen wenn:
- Korpus ist semantisch reich (Verträge, Forschungspapiere, Dokumentationen)
- Knowledge-Graph-Beziehungen wertvoll sind ("welche Verträge hängen mit Lieferant X zusammen?")
- Q&A mit Synthese aus mehreren Quellen gefragt ist
- Wir nutzen LightRAG intern produktiv (~440 Geschäftsdokumente indexiert)

## Pattern: Hybrid Search

Reine Vector-Similarity reicht selten. Produktiv kombinieren wir:

1. **Vector-Search** (pgvector HNSW oder Qdrant)
2. **Full-Text-Search** (PostgreSQL FTS oder Elasticsearch) — fängt Exact-Match und Domänen­vokabular
3. **Reciprocal Rank Fusion (RRF)** kombiniert die Rankings
4. **Reranker** (Voyage AI, Cohere Rerank, BGE) verbessert Top-K nochmal deutlich

Siehe Case Study Pet-Food-Avatar — exakt dieser Stack.

## Was wir explizit NICHT empfehlen

- **Pinecone** als Default für DACH-KMU — US-Vendor, DSGVO-Reibung, oft kein Mehrwert gegenüber pgvector
- **"Embedding everything"** ohne Chunking-Strategie — schlechte Chunks → schlechtes RAG, egal wie gut die DB ist
- **Fine-Tuning statt RAG** wenn das Wissen sich monatlich ändert — siehe `decision-matrices/rag-vs-fine-tuning.md`

## Embeddings-Modelle

- **nomic-embed-text** (lokal via Ollama) — 768 Dimensionen, EU-tauglich, kostenlos
- **Voyage AI** — sehr gute Reranker
- **OpenAI text-embedding-3** — Standard, gut, aber US-Anbieter

**Verwandt:**
- Self-Hosting: `tech-stack/self-hosting.md`
- RAG vs Fine-Tuning: `decision-matrices/rag-vs-fine-tuning.md`
