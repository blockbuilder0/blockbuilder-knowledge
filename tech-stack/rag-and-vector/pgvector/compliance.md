---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: rag-and-vector
tech: pgvector
---

# pgvector — Compliance

Stand 2026-05-20.

## DSGVO / GDPR

- **pgvector ist eine Postgres-Extension** — es selbst speichert nichts, führt keine Telemetrie aus, kontaktiert keine externen Server. Compliance richtet sich nach dem zugrundeliegenden Postgres-Deployment
- **Datenresidenz**: 100% bestimmt durch das gewählte Postgres-Hosting (on-prem, EU-Cloud, etc.)
- **DPA**: Nicht erforderlich für die Extension selbst. Falls Managed-Postgres genutzt wird, gilt der DPA des Hosters (AWS, Azure, Supabase, Neon, ...)

## EU AI Act

- pgvector ist kein KI-System. Es ist Speichertechnologie für Vektoren — wie Postgres selbst nicht reguliert
- Verantwortung verbleibt beim Gesamtsystem-Deployer

## Lizenz

- **PostgreSQL License** (BSD-ähnlich) — frei kommerziell nutzbar, keine Copyleft-Pflicht [Quelle: https://github.com/pgvector/pgvector/blob/master/LICENSE]

## Sicherheits-Eigenschaften

- Erbt alle Sicherheitsmechanismen von PostgreSQL: Row-Level Security, SSL/TLS, GSSAPI, RBAC, Logical Replication, Audit-Tooling (pgaudit)
- **Encryption at Rest**: über Postgres-Storage-Layer (LUKS, Cloud-Disk-Encryption)
- **Encryption in Transit**: über Postgres SSL
- **Backups**: über `pg_dump`, `pg_basebackup`, Streaming Replication, PITR — Vector-Daten sind normale Tabellenspalten

## Bezugswege und Compliance-Niveau

| Setup | Datenresidenz | DPA | Compliance-Niveau |
|---|---|---|---|
| Self-Hosted Postgres + pgvector (DACH-RZ) | beim Kunden | n/a | **maximal** |
| Azure Database for PostgreSQL + pgvector (EU) | EU | MS DPA | hoch (C5, ISO27001) |
| AWS RDS + pgvector (FRA) | EU | AWS DPA | hoch (C5, ISO27001) |
| Supabase (Hosted) | EU-Regionen verfügbar | Supabase DPA | mittel-hoch [Quelle: https://supabase.com/docs] |
| Neon (Hosted) | EU-Regionen verfügbar | Neon DPA | mittel-hoch [Quelle: https://neon.tech] |

## Branchen-Eignung

- Universell einsetzbar in allen DACH-B2B-Branchen
- Für § 203-StGB-Use-Cases: on-prem Postgres + pgvector
- Für Behörden: Open Source als Vergabeplus, on-prem oder STACKIT/OVH
