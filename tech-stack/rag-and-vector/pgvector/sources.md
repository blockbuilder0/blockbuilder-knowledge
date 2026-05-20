---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: rag-and-vector
tech: pgvector
---

# pgvector — Quellen

Alle URLs abgerufen 2026-05-20.

## Offizielle Quellen

- **GitHub Repository**: https://github.com/pgvector/pgvector
- **Lizenz (PostgreSQL License)**: https://github.com/pgvector/pgvector/blob/master/LICENSE
- **PostgreSQL Extension Network**: https://pgxn.org/dist/vector
- **Andrew Kane (Maintainer)**: https://github.com/ankane

## Verwandte Themen

- **HNSW Paper (Malkov & Yashunin)**: https://arxiv.org/abs/1603.09320
- **PostgreSQL Docs**: https://www.postgresql.org/docs/
- **pgvector-python**: https://github.com/pgvector/pgvector-python
- **pgvector-node**: https://github.com/pgvector/pgvector-node

## Bezugswege (Managed)

- **AWS RDS for PostgreSQL**: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_PostgreSQL.html
- **Azure Database for PostgreSQL**: https://learn.microsoft.com/en-us/azure/postgresql/
- **Google Cloud SQL for PostgreSQL**: https://cloud.google.com/sql/docs/postgres
- **Supabase**: https://supabase.com/docs/guides/database/extensions/pgvector
- **Neon**: https://neon.tech/docs/extensions/pgvector
- **Crunchy Bridge**: https://www.crunchydata.com/products/crunchy-bridge

## Alternativen-Vergleich

- **Qdrant**: https://qdrant.tech
- **Milvus**: https://milvus.io
- **Weaviate**: https://weaviate.io
- **Pinecone**: https://www.pinecone.io

## Verifizierte Fakten (Stand 2026-05-20)

- **HNSW-Defaults**: `m = 16`, `ef_construction = 64`, `ef_search = 40`. Höhere Werte verbessern Recall auf Kosten von Build-/Query-Zeit. Index sollte in den Memory passen (RAM-Sizing-Heuristik); für sehr große Datensätze stehen Half-Precision- und Binary-Quantization zur Verfügung [Quelle: https://github.com/pgvector/pgvector, abgerufen 2026-05-20]
- **Postgres-Tabellen-Limit**: Non-partitioned Tables haben in Postgres einen Default-Limit von 32 TB; Partitionierung kann das ausweiten [Quelle: https://github.com/pgvector/pgvector, abgerufen 2026-05-20]

## Noch zu prüfen

- Genauer Single-Node-Skalierungs-Sweetspot (50M vs. 100M Vektoren) *(Stand 2026-05-20: hardware- und use-case-abhängig — keine harten Grenzwerte im pgvector-README; abhängig von Embedding-Dimension, Index-Typ, RAM, NVMe-Latenz)*
