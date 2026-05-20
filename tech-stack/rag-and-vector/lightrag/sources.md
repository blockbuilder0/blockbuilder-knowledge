---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: rag-and-vector
tech: lightrag
---

# LightRAG — Quellen

Alle URLs abgerufen 2026-05-20.

## Offizielle Quellen

- **GitHub Repository**: https://github.com/HKUDS/LightRAG
- **Lizenz (MIT)**: https://github.com/HKUDS/LightRAG/blob/main/LICENSE
- **Paper (arXiv)**: https://arxiv.org/abs/2410.05779
- **Paper (EMNLP 2025)**: "LightRAG: Simple and Fast Retrieval-Augmented Generation" — Acceptance bestätigt, im Repo-Header ausgewiesen als `[EMNLP2025]` [Quelle: https://github.com/HKUDS/LightRAG, abgerufen 2026-05-20]
- **Project Page (HKUDS)**: https://github.com/HKUDS

## Verwandte Forschung

- **GraphRAG (Microsoft Research)**: https://github.com/microsoft/graphrag

## Storage Backends (verwendet)

- **pgvector**: https://github.com/pgvector/pgvector
- **Neo4j**: https://neo4j.com
- **Milvus**: https://milvus.io
- **Qdrant**: https://qdrant.tech

## BlockBuilder-interne Referenzen

- Deployment-Notes: BlockBuilder CLAUDE.md, Abschnitt "Knowledge Graph (LightRAG)"
- Skills: `/lightrag`, `/lightrag-index`
- Endpoint: http://192.168.2.100:9621 (intern, via WireGuard)
- Indexierte Dokumente: ca. 440, Entities ca. 7640

## Verifizierte Fakten (Stand 2026-05-20)

- **Aktuelles Upstream-Release**: v1.4.16 vom 07.05.2026 (71 Releases insgesamt, 35.4k GitHub-Stars) [Quelle: https://github.com/HKUDS/LightRAG, abgerufen 2026-05-20]
- **EMNLP 2025 Acceptance**: bestätigt — Paper-Titel im Repo-Header als `[EMNLP2025]` markiert
- **Unsere produktive Version**: BlockBuilder fährt aktuell LightRAG 1.4.13 (siehe BlockBuilder CLAUDE.md, Abschnitt "Knowledge Graph"); Upstream-Cadence ca. monatlich

## Noch zu prüfen

- Quantitativer Performance-Vergleich LightRAG vs. GraphRAG mit aktuellen Benchmarks *(Stand 2026-05-20: das Paper enthält Vergleiche zum GraphRAG-Stand 2024; neuere head-to-head-Benchmarks für GraphRAG 3.x liegen nicht öffentlich vor)*
