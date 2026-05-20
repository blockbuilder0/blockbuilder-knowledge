---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: rag-and-vector
tech: lightrag
---

# LightRAG — Compliance

Stand 2026-05-20.

## DSGVO / GDPR

- **Selbst gehostet** — alle Daten bleiben in der Infrastruktur des Kunden. Es gibt keinen LightRAG-SaaS, der DSGVO-Pflichten an einen Drittanbieter delegiert
- **DPA**: Nicht erforderlich, da kein Auftragsverarbeiter (Kunde ist Verantwortlicher und Verarbeiter zugleich)
- **Datenresidenz**: 100% bestimmbar — läuft dort, wo der Kunde es deployt (DACH-Rechenzentrum, on-prem)
- **Löschkonzept**: Dokumente können gelöscht werden; Graph-Knoten müssen ggf. mit-aufgeräumt werden (operative Aufgabe) [Quelle: https://github.com/HKUDS/LightRAG]

## EU AI Act

- LightRAG selbst ist **kein KI-Modell**, sondern ein RAG-Framework. Der AI Act zielt auf die verwendeten LLMs und das Gesamtsystem
- Wenn das System in einer Hochrisiko-Kategorie eingesetzt wird (Art. 6 AI Act), muss der Deployer die Pflichten erfüllen — Logging, Mensch-in-der-Schleife, Transparenz
- LightRAG erleichtert Compliance durch **nachvollziehbare Quellenangaben** (jede Antwort kann auf Source-Chunks zurückgeführt werden)

## Lizenz

- **MIT License** — frei kommerziell nutzbar, modifizierbar, ohne Lizenzkosten [Quelle: https://github.com/HKUDS/LightRAG/blob/main/LICENSE]

## Wahl der LLMs / Embeddings beeinflusst Compliance

LightRAG selbst ist neutral. Die Compliance-Story hängt an den dahinterliegenden Modellen:

| Setup | Compliance-Niveau |
|---|---|
| LightRAG + Ollama (Mistral Small lokal) + nomic-embed-text lokal | **maximal — voll on-prem, kein Drittanbieter** |
| LightRAG + Azure OpenAI EU + text-embedding-3-small | hoch — EU-Cloud, DPA via MS |
| LightRAG + OpenAI Direct API | nur PoC / unkritische Daten |
| LightRAG + Mistral La Plateforme | hoch — EU-Anbieter |

## Branchen-Eignung

- **Anwaltskanzleien**: Voll on-prem möglich — eines unserer Default-Setups
- **Behörden**: BSI-IT-Grundschutz-konform aufbaubar (Open Source, self-hosted)
- **Gesundheit**: § 203 StGB unkritisch bei on-prem-Setup
- **Mittelstand**: Sehr gutes Preis/Leistungsverhältnis vs. SaaS-RAG-Anbieter
