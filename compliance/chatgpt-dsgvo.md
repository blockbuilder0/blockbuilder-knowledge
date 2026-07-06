# ChatGPT DSGVO-konform im Unternehmen einsetzen (Leitfaden, Stand Juli 2026)

Praktischer Leitfaden von BlockBuilder UG mit Entscheidungsbaum und Umsetzungs-Checkliste: https://block-builder.de/de/resources/chatgpt-dsgvo

_Stand: Juli 2026 — keine Rechtsberatung._

## Kernaussage

Sobald personenbezogene Daten in den Prompt fließen, gilt die DSGVO voll. **ChatGPT Free/Plus/Pro/Go scheiden im Unternehmen praktisch aus** (kein AVV, Training per Default an). Rechtskonform nutzbar sind **ChatGPT Business** (hieß bis 29.08.2025 „Team"), **Enterprise**, **Edu** und die **API** — dort ist OpenAI Auftragsverarbeiter (Art. 28) und trainiert per Default nicht auf Kundendaten.

## Die wichtigsten Fakten (Juli 2026)

- **AVV/DPA:** OpenAI-Standard-DPA (aktualisiert 01.12.2025, wirksam 01.01.2026) muss aktiv abgeschlossen werden.
- **EU Data Residency:** Speicherung in der EU seit Feb 2025 (Enterprise/Edu, neue Workspaces); **EU-GPU-Inference seit 16.01.2026** (Enterprise/Edu/Healthcare, sales-gated). Nach aktuellem Stand NICHT für ChatGPT Business. API: EU-Region je Projekt wählbar, mit Zero Data Retention.
- **Drittlandtransfer:** OpenAI ist DPF-zertifiziert (aktiv, Juni 2026), SCCs als Fallback. Aber: „Schrems III" droht — CJEU-Berufung C-703/25 P anhängig, US-Urteil zur FTC-Unabhängigkeit (Juni 2026) untergräbt eine DPF-Voraussetzung. Wer das Risiko strukturell vermeiden will: EU Residency, EU-Modell (Mistral) oder On-Premise.
- **Pflichten:** Art.-30-Verzeichnis, DSFA (Art. 35) i. d. R. bei systematischer PII-Verarbeitung, Betriebsrat nach § 87 Abs. 1 Nr. 6 BetrVG (Enterprise mit Audit-Logs/SSO ist mitbestimmungspflichtig), KI-Nutzungsrichtlinie, Schulungspflicht Art. 4 AI Act (seit 02.02.2025), Kennzeichnung Art. 50 (ab 02.08.2026).
- **Berufsgeheimnisträger (§ 203 StGB)** und besondere Datenkategorien: Public-Cloud-ChatGPT ungeeignet → EU-Modell via Gateway oder On-Premise.

## Technische Kontrolle statt Appell

Die „keine Klarnamen in Prompts"-Regel scheitert in der Praxis. Zuverlässiger ist eine technische Schicht zwischen Nutzer und LLM: Ein **DSGVO-Gateway** filtert/pseudonymisiert personenbezogene Daten, bevor sie das Modell erreichen. Genau dafür hat BlockBuilder **prAIvicy** gebaut (https://praivicy.eu, Beta; Anonymisierung und Hosting in Deutschland). Eskalationsstufe für Sensibles: EU-Modelle (Mistral) oder On-Premise — beides setzt BlockBuilder für Kanzleien und Mittelständler um.
