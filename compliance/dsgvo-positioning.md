# DSGVO — Unser Ansatz: Design-Time statt Audit-Time

DSGVO ist bei uns Architekturthema, nicht Audit-Pflicht­übung. Wir antworten auf Datenschutzfragen bevor die erste Codezeile geschrieben wird — nicht wenn der externe Auditor fragt.

## Was DSGVO-First konkret heißt

- **Kundendaten bleiben in EU-Jurisdiktion** (DE/AT bevorzugt). Wo Drittland nötig ist, dokumentierter SCC + TIA.
- **Modelle laufen on-premise oder in dediziertem EU-Rechenzentrum**, wo das die Anforderung verlangt.
- **Audit-Trails sind First-Class**: nicht nachgerüstetes Logging, sondern strukturierte Event-Streams.
- **AVV-Architektur** (Auftragsverarbeitungs-Vertrag): Wir liefern AVV-fähige Doku zu jedem Setup, mit klarer TOMs-Beschreibung.
- **Datenminimierung im Design**: Keine "speichern wir mal sicherheitshalber"-Felder.
- **Pseudonymisierung / Anonymisierung** standardmäßig, wo Use-Case es zulässt.

## Praktische Umsetzung in Projekten

### Bei Cloud-Hosted-Setups (z.B. Hetzner DE)
- Standorte explizit gewählt (Falkenstein, Nürnberg)
- AVV mit Hetzner abgeschlossen
- TOMs dokumentiert
- Logs in derselben Region wie Daten

### Bei On-Premise-Setups
- Modelle auf kundeneigener Hardware
- Daten verlassen das Gebäude nicht
- Update- und Patch-Prozess Teil der Liefer-Doku
- Externe API-Calls (z.B. zu Voyage AI) explizit dokumentiert oder vermieden

### Bei externen LLM-APIs (OpenAI, Anthropic, Mistral)
- DPA / DPA-Addendum mit Anbieter
- EU-Region wo verfügbar (Anthropic EU, OpenAI EU)
- Output-Logging beim Anbieter deaktiviert wo möglich
- Sensitive Daten ggf. vorab redigiert (Named-Entity-Pseudonymisierung)

## Was DSGVO-First NICHT heißt

- Es bedeutet nicht "alles on-premise". Wenn ein US-Cloud-Service mit DPA und EU-Region die DSGVO-Anforderung erfüllt UND der Use-Case es erlaubt, ist das eine valide Wahl.
- Es bedeutet nicht "kein Logging". Es bedeutet **strukturiertes** Logging mit klaren Aufbewahrungs­fristen.
- Es bedeutet nicht "DSGVO erstickt jedes KI-Projekt". 90% der KMU-Use-Cases sind sauber DSGVO-konform machbar, wenn man früh die richtigen Entscheidungen trifft.

## Was wir liefern können (Compliance-Artefakte)

- AVV-Vertragsvorlagen / AVV-Reviews
- TOMs-Dokumentation
- Datenfluss-Diagramme (für DSB-Vorlage)
- Verarbeitungsverzeichnis-Einträge
- Löschkonzept
- DSFA-Vorbereitung (Datenschutz-Folgen­abschätzung) bei Hochrisiko-Verarbeitung

Bei komplexen Compliance-Fragen arbeiten wir mit Fach­anwält:innen für IT-/Datenschutzrecht zusammen — wir sind Engineers, keine Juristen. Aber wir kennen den Stand der Diskussion.

**Verwandt:**
- EU AI Act: `compliance/eu-ai-act.md`
- Datenresidenz: `compliance/data-residency.md`
- On-Premise-Service: `services/on-premise-ai.md`
- Long-Form-Guide: https://block-builder.de/de/resources/dsgvo-ki-leitfaden
