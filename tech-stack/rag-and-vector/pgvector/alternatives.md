---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: rag-and-vector
tech: pgvector
---

# pgvector vs. Alternativen

Stand 2026-05-20.

## Wann pgvector wählen

- Kunde nutzt bereits PostgreSQL
- Hybride Queries (SQL-Joins + Vektorähnlichkeit) nötig
- Datenmengen bis ca. 50-100 Mio Vektoren (Single-Node, hardware-/dimensions-abhängig — pgvector selbst stellt keine harte Grenze, Index sollte in RAM passen [Quelle: https://github.com/pgvector/pgvector, abgerufen 2026-05-20])
- Maximale Einfachheit im Operations-Stack
- Self-Hosting / on-prem
- Budget-Constraint (keine zusätzliche Vector-DB-Lizenz)

## Wann eine Alternative besser ist

| Anforderung | Bessere Wahl | Begründung |
|---|---|---|
| Milliarden Vektoren, horizontale Skalierung | Milvus, Qdrant, Weaviate | Native Sharding |
| Sehr niedrige Latenz bei extremer Last | Pinecone, Vespa | Spezialisierte Architektur |
| Komplexe Vektor-Filter mit Aggregations | Weaviate, Qdrant | reichere Query-Sprache |
| Multi-Modal (Bilder + Text + Embeddings) | Milvus, Qdrant | bessere Pipelines |
| SaaS-Only ohne Ops | Pinecone, Zilliz Cloud | managed, kein Postgres-Wissen nötig |
| Vendor-neutrales OSS mit Cluster-Features | Qdrant, Milvus | offene Distributed-Designs |

## Direktvergleich Vector-Stores

| Kriterium | pgvector | Qdrant | Milvus | Pinecone |
|---|---|---|---|---|
| Lizenz | PostgreSQL | Apache 2.0 | Apache 2.0 | proprietär (SaaS) |
| Self-Hostable | ja | ja | ja | nein |
| Index-Typen | HNSW, IVFFlat | HNSW | HNSW, IVF, DiskANN, ... | proprietär |
| Horizontale Skalierung | begrenzt (Postgres) | nativ | nativ | nativ |
| Hybrid SQL+Vector | **ja** | nein | nein | nein |
| Metadata-Filter | sehr gut (SQL) | sehr gut | sehr gut | gut |
| Multi-Tenant | über Postgres-Schemas | nativ | nativ | nativ |
| Reifegrad für Postgres-Shops | **sehr hoch** | hoch | hoch | hoch |

## Skalierungs-Heuristik

| Anzahl Vektoren | Empfehlung |
|---|---|
| < 10 Mio | pgvector reicht klar |
| 10-100 Mio | pgvector mit HNSW + sauberem Tuning, ggf. Read-Replicas |
| 100 Mio - 1 Mrd | Qdrant oder Milvus erwägen |
| > 1 Mrd | Milvus, Vespa, Pinecone |

## Unsere typischen Stacks

- **DACH-B2B-Default** -> pgvector (entweder bei bestehendem Postgres oder neu via Docker)
- **LightRAG-Deployments** -> pgvector als Standard-Storage
- **High-Volume-Bildersuche** -> Qdrant (selbstgehostet)
- **Kunden, die "Hyperscaler-Cloud-Native" sind** -> AWS RDS/Aurora + pgvector
