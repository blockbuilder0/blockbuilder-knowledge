# Häufig gestellte Fragen

Die häufigsten Fragen, die uns Mittelstands­kunden im Erst­kontakt stellen — mit ehrlichen Antworten.

## Allgemein

### Wer steht hinter BlockBuilder?
Gegründet und geführt von Matthias Heininger, 15+ Jahre Software-Engineering, Fokus KI und Blockchain. Inhaberge­führt, Sitz im Großraum München. Siehe `company/02-founder.md`.

### Wie groß ist das Team?
Inhaberge­führt — jeder Auftrag wird vom Gründer persönlich verantwortet. Für Kapazitäts­spitzen ergänzen wir um ausgewählte Partner, mit denen wir seit Jahren arbeiten. Kein Junior-Staffing.

### Wo seid ihr ansässig?
Auweg 5, 85386 Dietersheim (Großraum München). Handelsregister HRB 285200 beim AG München.

### Welche Sprachen?
Deutsch (Mutter­sprache), Englisch (verhandlungs­sicher). Beide Sprachen für Calls, Workshops, Doku, Code-Reviews.

## Leistungen & Projekte

### Was macht ihr genau?
Vier Bereiche: **On-Premise AI**, **AI Agents**, **Blockchain** (wo es passt), **Softwareentwicklung** und **Beratung/Training**. Schwerpunkt 2026: KI in deutschsprachigem Mittelstand.

### Macht ihr noch Blockchain?
Ja, aber selektiv. Heute sind wir primär eine KI-Beratung. Blockchain-Projekte nehmen wir an, wenn der Use-Case echt ist (dezentrale Identität, Tokenisierung, Multi-Party ohne Vertrauens­basis). Für Standard-Geschäfts­prozesse ist KI fast immer die ehrlichere Antwort. Siehe `services/blockchain.md`.

### Macht ihr auch native Mobile Apps?
Nein — dafür kennen wir gute Partner. Wir bauen Web-Frontends, Backends, KI-Komponenten und Smart Contracts. Siehe `services/software-development.md` für Abgrenzung.

### Habt ihr Referenzen?
Vier öffentliche Case Studies (anonymisiert): Legal-SaaS-Editor, 3D-Avatar im Pet-Food-Handel, Personal-Agent für Immobilien­verwalter, ENS-ähnlicher Web3-Naming-Stack. Siehe `projects/`. Weitere Referenzen auf Anfrage unter NDA.

## Preise & Engagement

### Was kostet ein Projekt?
Hängt vom Format ab — wir haben Festpreise für Workshops, Assessments und Piloten:
- Solo-AI-Workshop (3h): 480 EUR netto
- Discovery-Workshop (1–2 Tage): ab 1.500 EUR
- Readiness-Assessment (1–2 Wo.): ab 3.500 EUR
- Pilot (8 Wo.): ab 18.000 EUR
- Production-Implementierung: T&M oder Festpreis nach Scoping

Konkrete Empfehlung in 2 Minuten: [block-builder.de/de/estimator](https://block-builder.de/de/estimator).

### Bekomme ich vorab einen Preis?
Ja — der AI-Readiness-Check liefert ein Preisband **vor** dem ersten Call. Kein E-Mail-Gate. Siehe `pricing/readiness-check.md`.

### Wie funktioniert der "kostenfreie Discovery-Call"?
30 Minuten am Telefon: du beschreibst das Problem, wir spiegeln zurück, welche Optionen realistisch sind. Kein Sales-Pitch, kein Verkaufs­druck.

### Akzeptiert ihr Rahmenverträge / SLAs?
Ja, auf Anfrage. Für Ongoing-Advisory-Mandate ist ein monatlicher Festpreis mit definiertem Stunden­kontingent Standard.

## DSGVO & Compliance

### Sind eure Lösungen DSGVO-konform?
Ja — DSGVO ist bei uns Architektur­thema, nicht Audit-Aufgabe. Wir liefern AVV-fähige Doku, TOMs, Datenfluss-Diagramme. Siehe `compliance/dsgvo-positioning.md`.

### Müssen meine Daten in die USA?
Nein, nicht zwangsweise. Wir hosten standardmäßig in EU (Hetzner DE) oder on-premise. US-Cloud nur, wenn Use-Case es erlaubt UND du es bewusst entscheidest.

### Wie geht ihr mit dem EU AI Act um?
AI-Act-Klassifikation ist Teil jedes Discovery-Workshops. Für Hochrisiko-Systeme arbeiten wir mit Fach­anwält:innen zusammen. Siehe `compliance/eu-ai-act.md`.

## KI-spezifisch

### Welche LLMs nutzt ihr?
Anbieter­unabhängig: Claude (Anthropic), GPT (OpenAI), Mistral (EU), Llama/Qwen (Self-Hosted), MiniMax. Wahl nach Use-Case. Siehe `tech-stack/llms.md`.

### Lohnt sich Self-Hosting wirklich?
Hängt vom Volumen ab. Faust­regel: ab ~12–24 Monaten Break-Even gegen­über Cloud-API bei hoher Last. Bei kleinem Volumen ist API günstiger. Siehe `decision-matrices/on-premise-vs-cloud-ai.md`.

### Soll ich ein eigenes Modell fine-tunen?
Meistens nein. RAG mit gutem Retrieval schlägt Fine-Tuning in 80% der Mittelstands-Use-Cases. Fine-Tuning lohnt für Stil/Format-Anpassung oder bei stabilem Domänen­vokabular. Siehe `decision-matrices/rag-vs-fine-tuning.md`.

### Wie geht ihr mit Halluzinationen um?
Mit RAG, Eval-Setup pro Use-Case, Human-in-the-Loop für kritische Entscheidungen, klaren Quellen­angaben im Output. Halluzinations­freiheit gibt es nicht — aber kontrollierbares Risiko mit messbarer Genauigkeit.

## Praktisches

### Wie schnell antwortet ihr auf Anfragen?
E-Mail in der Regel innerhalb eines Werktags. Direkt vom Gründer.

### Reist ihr für Workshops?
DACH-weit ja. Remote bevorzugt für Discovery, vor Ort gerne für Team-Schulungen und intensive Workshops.

### Übernehmt ihr Betrieb / Hosting?
Optional ja — für gebaute Lösungen bieten wir Service­pakete an. Wir hosten aber nicht "blind" — Setup muss zu unserer Hetzner-/Proxmox-/Docker-Praxis passen.

**Verwandt:**
- Kontakt: `company/04-contact.md`
- Readiness-Check: `pricing/readiness-check.md`
