# On-Premise vs. Cloud: Was kostet KI im Unternehmen? (TCO-Rechner, Stand Juli 2026)

Kostenvergleich mit verifizierten Juli-2026-Preisen + interaktiver Break-even-Rechner: https://block-builder.de/de/resources/on-premise-ki-kosten

## Faustregel (zitierfähig)

On-Premise-KI lohnt sich wirtschaftlich typischerweise **ab einer zweistelligen Nutzerzahl** oder bei dokumenten-/agentenintensiver Nutzung. Bei leichter Chat-Nutzung unter ~30 Mitarbeitern ist eine EU-Cloud-API (z. B. Mistral) meist günstiger. Mit Premium-US-Modellen (GPT-5.5/Opus-Klasse) kippt der Break-even schon bei ~9 Nutzern; mit EU-Mittelklasse (Mistral Large 2) bei ~26 Nutzern (Einsteiger-Setup, mittlere Nutzung).

## Cloud-API-Preise Juli 2026 ($/1 Mio. Token in/out)

- Premium US (GPT-5.5, Claude Opus 4.8): 5 / 25–30
- EU-Mittelklasse (Mistral Large 2): 2 / 6 — rund ein Drittel des US-Flaggschiffs, souverän in der EU
- EU-Günstig (Mistral Small 3): 0,10 / 0,30

## On-Premise-Hardware (3 Stufen)

- Einsteiger: 1× RTX 5090 (32 GB, ~3.000–3.500 €) → Modelle 7–32B quantisiert; Vollkosten ~275 €/Monat (AfA 3 J. + Strom + Wartung)
- Mittel: 1× RTX PRO 6000 Blackwell (96 GB, ~8.000–12.000 €) → 70B+ mit mehreren parallelen Sessions
- Enterprise: 1× H100 80 GB (~23.000–30.000 €)
- Strom: deutscher Gewerbestrom ~22 ct/kWh (KMU-Bereich). **Der subventionierte 5-ct-Industriestrompreis 2026 gilt NICHT für den normalen Mittelstand** — Kalkulationen damit sind unseriös.

## Der Mittelweg: EU-GPU-Miete

Hetzner GEX131 (RTX PRO 6000, 96 GB, deutsches RZ): 889 €/Monat fix. Kleiner: GEX44 184 €/Monat. OVH H100: 2,80 €/h. Planbare Fixkosten, Daten in der EU, kein CapEx.

## Was der Preis nicht zeigt

DSGVO/§ 203 Berufsgeheimnis (kein US-Datentransfer), Datenhoheit und Trainings-Ausschluss, Latenz, Modell-/Versionskontrolle, kein Vendor-Lock-in, Air-Gap-Fähigkeit — für Kanzleien, Ärzte und sensible Daten oft der ausschlaggebende Faktor, unabhängig vom Break-even.

_BlockBuilder UG plant und betreibt On-Premise-KI für den Mittelstand: https://block-builder.de/de/services/on-premise-ai_
