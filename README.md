# BlockBuilder Knowledge Base

Kuratierte Wissensbasis für den Chatbot auf [block-builder.de](https://block-builder.de). Quelle für eine LightRAG-Instanz, die Antworten auf Besucherfragen liefert.

## Zweck

Dieses Repository ist die **einzige Wahrheitsquelle** für inhaltliche Aussagen, die der Website-Chatbot über BlockBuilder UG, ihre Services, Projekte, Preise und Positionierung macht. Es ergänzt die SSR-Inhalte auf block-builder.de um tiefere Erklärungen, Entscheidungshilfen und FAQ-Antworten.

## Indexierung

- Inhalte werden als Markdown gepflegt — eine Datei = ein semantisches Thema.
- Sprache: **Deutsch**. EN-Antworten werden vom LLM zur Laufzeit übersetzt.
- LightRAG indexiert das Repo periodisch (siehe `/lightrag-index` Skill im BlockBuilder-UG-Workspace).
- Pro Datei 200–500 Wörter, klare H2/H3-Struktur, Bullet-Listen wo sinnvoll.

## Pflege

- Änderungen via Pull Request.
- Keine Marketingfloskeln ("revolutionär", "best-in-class") — nüchterner, ehrlicher Ton.
- Pro Service-Datei ein Abschnitt "Wofür eignet sich das NICHT?" — Vertrauen entsteht durch Abgrenzung.
- Quellenangaben/Cross-Refs am Dateiende unter `**Mehr dazu:**` oder `**Verwandt:**`.

## Was hier NICHT hingehört

- Kundennamen, Vertragsvolumina, NDA-Inhalte
- Interne Roadmaps, Sprint-Pläne, Personalfragen
- Konkrete Preise jenseits der öffentlich kommunizierten Bänder (Solo-Workshop 480 EUR, Assessment ab 3.500 EUR etc.)
- Inhalte aus `/home/heiningair/Documents/docs/Geschäftlich/` (Buchhaltung, Steuern, gopass-Pfade) — die bleiben im internen Workspace.

## Struktur

| Ordner | Inhalt |
|---|---|
| `company/` | Pitch, Gründerbio, Prinzipien, Kontakt |
| `services/` | Tiefenbeschreibung der 5 Leistungsbereiche |
| `projects/` | 4 anonymisierte Case Studies |
| `tech-stack/` | LLMs, Agent-Frameworks, RAG, Self-Hosting, Infra |
| `compliance/` | DSGVO, EU AI Act, Datenresidenz |
| `pricing/` | Readiness-Check, Preisphilosophie, Engagement-Modelle |
| `faq/` | Häufige Mittelstandsfragen |
| `decision-matrices/` | Entscheidungshilfen (Blockchain vs AI, On-Prem vs Cloud, RAG vs FT) |
