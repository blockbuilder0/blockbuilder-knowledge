# Blockchain vs AI — Welches Werkzeug für welches Problem?

Beide Techno­logien sind mächtig. Beide werden regelmäßig am falschen Problem ein­gesetzt. Diese Matrix hilft bei der ehrlichen Wahl.

## Faustregel

> **Blockchain ist die richtige Antwort, wenn das Problem von Natur aus Multi-Party-ohne-Vertrauen ist. Für fast alles andere ist KI das ehrlichere Werkzeug.**

## Wann Blockchain genuinely passt

- **Multi-Party ohne gemeinsame Vertrauens­basis**: mehrere Organisationen müssen kooperieren, aber keiner soll als zentraler Vertrauens­anker auftreten
- **On-Chain-Verifizierbarkeit**: Beweise müssen Dritten ohne Trust-in-Operator nach­weisbar sein (z.B. Echtheit von Zertifikaten, Liefer­ketten-Provenance)
- **Tokenisierung**: Werte oder Rechte werden in handel­baren oder programmier­baren Einheiten ausgegeben (Membership, Asset-Anteile, Loyalty-Punkte mit Sekundär­markt)
- **Dezentrale Identität / Self-Sovereign Identity**: Benutzer sollen ihre Credentials selbst halten, nicht beim Anbieter

## Wann KI fast immer die bessere Antwort ist

- **Interne Prozesse automatisieren** (Rechnungs­prüfung, E-Mail-Triage, Berichts­erstellung)
- **Dokumenten­basierte Workflows** (Anträge klassifizieren, Verträge analysieren, Belege strukturieren)
- **Sprach­verarbeitung** (Kunden­service, Voice-UI, Trans­kription)
- **Personalisierung** (Empfehlungen, kontext­sensitive Antworten)
- **Mustererkennung in Daten** (Anomalie­detektion, Forecasts, Klassifikation)

## Entscheidungs­matrix

| Frage | Wenn JA → | Wenn NEIN → |
|---|---|---|
| Müssen mehrere Parteien ohne gemeinsame Vertrauens­basis kooperieren? | Blockchain prüfen | Wahrscheinlich kein Blockchain-Case |
| Müssen Beweise Dritten ohne Trust-in-Operator verifiziert werden? | Blockchain prüfen | Append-only-DB mit Signaturen reicht oft |
| Werden Werte/Rechte tokenisiert mit offenem Sekundär­markt? | Blockchain prüfen | Klassische DB reicht |
| Geht es um Sprache, Dokumente, Klassifikation, Personalisierung? | KI prüfen | — |
| Geht es um regelbasierte Workflows mit klaren Schritten? | Workflow-Tool (n8n, Make), nicht KI | — |

## Häufige Misuse-Patterns

### "Wir tokenisieren unser Loyalty-Programm"
Wenn es keinen Sekundär­markt und keine Multi-Party-Interaktion gibt, ist eine klassische Datenbank besser auditierbar, billiger im Betrieb und gibt rechtlich weniger Reibung.

### "Blockchain für Audit-Logs"
Append-only-Datenbank mit kryptographisch signierten Einträgen leistet 95% dessen, was die meisten Audit-Use-Cases brauchen — ohne Smart-Contract-Komplexität.

### "KI für unsere Geschäfts­regeln"
Wenn die Regeln in einem Word-Dokument stehen ("Wenn Rechnungs­summe > 1000 EUR, dann Freigabe durch Bereichs­leiter"), gehören sie in eine Decision-Tabelle oder ein Workflow-Tool — nicht in einen LLM-Prompt.

### "KI-Agent für deterministische ETL"
Wenn die Trans­formation klar definiert ist, mach es mit SQL/Python/dbt. KI-Agenten sind teuer, lang­samer und nicht-deterministisch.

## Zusammen­fassung

| Problem-Charakter | Wahl |
|---|---|
| Multi-Party-Trust-Problem | Blockchain |
| Sprache / Doku / Personali­sierung / Muster | KI |
| Klare Regeln, deter­ministisch | Workflow-Tool / klassische Software |
| Reine Datenbank-Auditier­barkeit | Append-only-DB |

**Verwandt:**
- Blockchain-Service: `services/blockchain.md`
- AI-Agents-Service: `services/ai-agents.md`
- Case Study ENS-ähnlich: `projects/ethereum-name-service.md`
