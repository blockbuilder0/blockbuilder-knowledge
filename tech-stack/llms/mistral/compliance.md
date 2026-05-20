---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: mistral
---

# Mistral — Compliance für DACH-B2B

Stand 2026-05-20. Verbindliche Aussagen mit Mistral Trust Center abgleichen [Quelle: https://trust.mistral.ai].

## DSGVO / GDPR

- **EU-Anbieter**: Mistral AI SAS, Sitz Paris, Frankreich. Unterliegt direkt der DSGVO — keine Drittstaaten-Transfer-Diskussion nötig [Quelle: https://mistral.ai]
- **EU-Hosting**: La Plateforme verarbeitet in der EU [Quelle: https://mistral.ai/news/la-plateforme/]
- **DPA**: Verfügbar für alle La-Plateforme-Kunden
- **Kein Training auf Kunden-Daten**: API-Inputs/Outputs werden per Default nicht zum Training verwendet [Quelle: https://mistral.ai/terms/]
- **Zero Data Retention**: Standardmäßig minimale Retention; ZDR vertraglich möglich *(Stand 2026-05-20: konkrete ZDR-Konditionen nicht öffentlich im Trust Center dokumentiert — vor Quote bei Mistral-Sales klären [Quelle: https://trust.mistral.ai, abgerufen 2026-05-20])*

## EU AI Act

- Mistral ist als EU-Anbieter eng am AI Act ausgerichtet
- Mistral Large fällt unter GPAI; ob "systemisches Risiko" greift, hängt vom 10^25-FLOPs-Trainings-Threshold gemäß AI Act Art. 51 ab — Mistral hat die exakten Trainings-FLOPs für Large 3 nicht öffentlich publiziert *(Stand 2026-05-20: nicht öffentlich dokumentiert, manuell zu prüfen)*
- Modellkarten und Sicherheits-Evaluationen werden veröffentlicht [Quelle: https://docs.mistral.ai]
- Open-Weights-Modelle (Apache 2.0) haben besondere Status im AI Act (z. T. erleichterte Pflichten)

## Zertifikate

- **SOC 2 Type II** [Quelle: https://trust.mistral.ai]
- **ISO 27001** *(Stand 2026-05-20: Trust-Center-Inhalt liefert per WebFetch nur die Page-Headline, nicht die Zertifikatsliste — manuell auf https://trust.mistral.ai bzw. via Mistral-Compliance-Kontakt verifizieren)*
- **BSI C5** — Stand 2026-05-20 nicht direkt für La Plateforme; über Azure AI Foundry (Mistral on Azure) erreichbar

## Bezugswege im Vergleich

| Pfad | Datenresidenz | DPA | Zertifikate | Empfehlung |
|---|---|---|---|---|
| Mistral La Plateforme | EU (FR) | ja | SOC2 | **bestes EU-Sovereign Cloud Setup** |
| Azure AI Foundry (EU) | EU (DE/FR/SE) | über MS DPA | C5, ISO27001 | wenn Kunde Azure-Setup hat |
| Self-Hosted (Ollama/vLLM) | beim Kunden | n/a | je nach Kunden-Stack | für maximale Souveränität |

## Branchen-Eignung

- **Anwaltskanzleien (§ 203 StGB)**: **Self-Hosted Mistral Small via Ollama** ist unser empfohlener Default
- **Finanzen/Versicherung**: La Plateforme oder Azure-Mistral darstellbar; BaFin-Auslagerung
- **Öffentliche Hand**: Self-Hosted oder Azure-Mistral mit BSI C5; "EU made" ist Vergabe-Plus
- **Mittelstand mit Souveränitätsanspruch**: Mistral ist häufig der politische Wunsch-Vendor

## Souveränitäts-Erzählung (Vertrieb)

Mistral ist Stand 2026-05-20 der einzige größere LLM-Anbieter, der **EU-Sitz + EU-Hosting + Open-Weights** kombiniert. Für DACH-Vergaben mit "kein US-Anbieter"-Klausel ist Mistral oft die einzige produktionsreife Option.
