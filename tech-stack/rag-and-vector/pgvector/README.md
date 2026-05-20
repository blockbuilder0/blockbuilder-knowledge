---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: rag-and-vector
tech: pgvector
---

# pgvector

## Was ist das?

pgvector ist eine **Open-Source-Erweiterung für PostgreSQL**, die Vector-Datentypen, Ähnlichkeitssuche und Vector-Indizes (HNSW und IVFFlat) hinzufügt. Damit wird jede PostgreSQL-Datenbank zu einer Vektor-Datenbank — ohne separaten Service [Quelle: https://github.com/pgvector/pgvector]. Maintained von Andrew Kane, PostgreSQL-Lizenz.

## Warum wir pgvector einsetzen

- **Ein System statt zwei**: Kunden haben oft schon Postgres laufen. Statt zusätzlich Pinecone/Weaviate/Qdrant zu betreiben, bleibt der Stack einfach
- **ACID + Vektorsuche kombiniert**: Klassische SQL-Joins über Metadaten + Vektorähnlichkeit in einer Query — kein verteiltes Konsistenz-Problem
- **Self-Hostable, Open Source**: PostgreSQL-Lizenz, frei kommerziell nutzbar [Quelle: https://github.com/pgvector/pgvector/blob/master/LICENSE]
- **HNSW-Index**: Hierarchical Navigable Small World — Stand der Technik für schnelle Approximate Nearest Neighbor Search [Quelle: https://github.com/pgvector/pgvector#hnsw]
- **Verfügbar in allen relevanten Managed-Postgres**: AWS RDS, Azure Database for PostgreSQL, Google Cloud SQL, Supabase, Neon, Crunchy Bridge
- **Solides Tooling**: Bindings für alle Major-Sprachen, Drizzle/Prisma/SQLAlchemy unterstützen es

## Wie wir pgvector integrieren

- **Default-Vector-Store** in LightRAG-Deployments
- **Standalone-RAG**: Schema mit `id, content, embedding vector(768)` + HNSW-Index, Cosine-Distance für Similarity
- **Hybrid Search**: Kombination aus pgvector (semantisch) + Postgres FTS (lexikalisch, ts_vector) über Rank-Fusion
- **Embeddings**: 768 Dim (nomic-embed-text) oder 1536 Dim (text-embedding-3-small)
- **Kunden-Stacks**: Wenn ein Kunde bereits Postgres hat (Supabase, RDS, on-prem), ist pgvector immer unsere erste Wahl

## Fähigkeiten

- **Datentypen**: `vector`, `halfvec`, `bit`, `sparsevec` [Quelle: https://github.com/pgvector/pgvector]
- **Distanzfunktionen**: L2 (`<->`), Inner Product (`<#>`), Cosine (`<=>`), L1 (`<+>`)
- **Indizes**: HNSW (besser für Production), IVFFlat (kleiner Speicherbedarf, brauchbar)
- **Max Dimensionen**: 16.000 (Vector), 4.000 (Index) [Quelle: https://github.com/pgvector/pgvector#vector-type]

## Wofür eignet sich pgvector NICHT?

- **Milliarden Vektoren mit harten Latenz-SLAs**: Dedizierte Vector-DBs (Milvus, Qdrant, Pinecone) skalieren horizontal eleganter
- **Sehr hochfrequente Updates** auf riesigen Indizes: HNSW-Rebuild ist nicht trivial
- **Reine Inferenz-Pipelines ohne SQL-Bedarf**: Overhead der relationalen Datenbank lohnt sich nicht
- **Multi-Tenant mit komplettem Index-Isolations-Bedarf**: Eigene Postgres-Cluster pro Tenant werden teuer
