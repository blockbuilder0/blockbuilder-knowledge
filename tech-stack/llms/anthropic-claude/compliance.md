---
last_updated: 2026-05-20
verify_sources_before_quoting: true
category: llms
tech: anthropic-claude
---

# Claude — Compliance für DACH-B2B

Stand 2026-05-20. Verbindliche Aussagen immer mit Anthropics Trust Center und dem aktuellen DPA abgleichen [Quelle: https://trust.anthropic.com].

## DSGVO / GDPR

- **Auftragsverarbeitungsvertrag (DPA)**: Anthropic stellt einen DPA bereit. Verfügbar via Trust Center bzw. Sales-Kontakt für Enterprise; bei API-Self-Service über das Console-Onboarding [Quelle: https://trust.anthropic.com]
- **Datenresidenz EU**: Direkter Anthropic-API-Zugang nutzt US-Infrastruktur. Für EU-Datenresidenz routen wir Kunden über **AWS Bedrock Region Frankfurt (eu-central-1)** [Quelle: https://aws.amazon.com/bedrock]
- **Kein Training auf Kunden-Daten**: Anthropic trainiert per Default nicht auf API-Inputs/Outputs zahlender Kunden [Quelle: https://www.anthropic.com/legal/commercial-terms]
- **Retention**: API-Logs werden standardmäßig 30 Tage gespeichert, für Trust-&-Safety-Prüfung. Zero Data Retention (ZDR) ist für qualifizierte Kunden vertraglich verfügbar *(Stand 2026-05-20: die genauen Qualifikationskriterien für ZDR sind nicht öffentlich im Trust Center dokumentiert — vor Quote bei Anthropic-Sales klären [Quelle: https://trust.anthropic.com, abgerufen 2026-05-20])*

## EU AI Act

- Anthropic-Modelle fallen unter GPAI (General-Purpose AI). Opus 4.7 könnte in die Kategorie "GPAI mit systemischem Risiko" fallen (>10^25 FLOPs Training) — Anthropic publiziert hierzu Modellkarten und Risiko-Assessments [Quelle: https://www.anthropic.com/responsible-disclosure-policy]
- Anwender-Compliance (Hochrisiko-Use-Cases, Transparenzpflichten Art. 50) bleibt **Verantwortung des Deployers**, also unseres Kunden. Wir unterstützen mit Dokumentation

## Bezugswege im Vergleich

| Pfad | Datenresidenz | DPA | C5/ISO27001 | Empfehlung |
|---|---|---|---|---|
| Anthropic Direct API | US | ja | ISO 27001, SOC 2 | OK für interne PoCs |
| AWS Bedrock Frankfurt | EU (DE) | über AWS DPA | C5, ISO27001, SOC2 | **Default für DACH-Kunden** |
| Google Vertex AI eu | EU | über GCP DPA | ISO27001, SOC2 | gut, falls Kunde bereits GCP nutzt |

## Branchen-Eignung

- **Finanzen / Versicherung**: nutzbar via Bedrock, BaFin-relevant: Auslagerungs-Anzeige erforderlich
- **Gesundheit (KHZG/PDSG)**: nur über Bedrock + zusätzliche Verschlüsselung; kein BAA äquivalent in DE — Einzelfallprüfung
- **Öffentliche Hand**: BSI-C5-Testat via AWS Bedrock, nicht via Direct API. IT-Grundschutz-Mapping individuell zu klären
- **Anwaltskanzleien**: § 203 StGB-Prüfung individuell — wir empfehlen on-prem-Lösung (Mistral/Ollama) als Alternative
