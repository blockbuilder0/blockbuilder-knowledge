# RAG vs Fine-Tuning — Wann was?

Eine der häufigsten Fragen im Erst­gespräch. Die ehrliche Antwort: **In 80% der Mittelstands-Use-Cases ist RAG die richtige Antwort. Fine-Tuning hilft bei Stil/Format, selten beim Wissen.**

## Kurz­fassung

| Ziel | Werkzeug |
|---|---|
| Modell soll **Fakten/Daten** wissen, die sich ändern können | **RAG** |
| Modell soll im **bestimmten Stil/Format** antworten | **Fine-Tuning** |
| Modell soll **domänen­spezifisches Vokabular** verstehen | meistens RAG, manchmal Fine-Tuning |
| Modell soll **strukturierte Outputs** zuverlässig liefern | Constrained Generation / JSON-Mode, selten Fine-Tuning |
| Modell soll **schneller / billiger** werden | Modell-Wahl (kleineres Modell), evtl. Fine-Tuning eines kleineren Modells |

## Warum RAG meistens gewinnt

1. **Daten ändern sich**: Verträge werden aktualisiert, Produkte ändern sich, Prozesse werden überarbeitet. Fine-Tuning friert Wissen ein.
2. **Audit-Trail**: RAG liefert Quellen­angaben. Fine-Getunte Antworten kommen aus dem Modell-Inneren — nicht nachvollziehbar.
3. **Datenschutz**: Trainings­daten zu pseudonymisieren ist aufwändig. Bei RAG kann Zugriff pro Dokument/Nutzer kontrolliert werden.
4. **Kosten**: RAG-Setup ist günstiger als Fine-Tuning-Pipeline (Trainings­daten kuratieren, GPU-Training, Eval, Re-Deployment).
5. **Reversibilität**: RAG-Updates sind Indexierung. Fine-Tune-Fehler sind ein neues Modell.

## Wann Fine-Tuning trotzdem hilft

- **Stil-Anpassung**: Modell soll konsistent in Hausstil schreiben (Tonalität, Anrede, Format)
- **Strukturierte Domänen­sprache**: Modell soll fach­spezifische Notation zuverlässig verwenden (medizinische Codes, juristische Formulare)
- **Latenz / Kosten**: Kleines fein-getuntes Modell schlägt großes Base-Modell + langen Prompt bei stabiler Aufgabe
- **Few-Shot reicht nicht mehr**: Wenn der Prompt mit Beispielen zu groß und zu instabil wird

## Hybrid-Pattern (häufig die beste Antwort)

Fine-Tuning für **Stil und Verhalten** (kleines Modell, einmaliges Training), RAG für **aktuelles Wissen** (laufend indexierte Quellen).

Beispiel: Ein juristischer Schreib-Assistent wird auf den Hausstil einer Kanzlei fein-getunt (formelle Anrede, Zitations­format) und erhält über RAG Zugriff auf die aktuellen Mandant:innen-Akten.

## Anti-Pattern: "Fine-Tunen, damit das Modell unsere Daten kennt"

Das ist meist der falsche Weg. Wenn ein Modell auf Firmen­daten fine-getunt wurde, kann es:
- Daten beim Inferenz "auspusten" (Daten­schutz-Risiko)
- Neue Daten nicht ohne Re-Training lernen
- Quellen nicht zitieren
- Halluzinieren, ohne dass man die Quelle prüfen kann

RAG vermeidet alle vier Probleme.

## Entscheidungs­fragen

1. **Ändert sich das Wissen?** Ja → RAG. Nein → Fine-Tuning möglich.
2. **Brauchst du Quellen­angaben?** Ja → RAG. Nein → Fine-Tuning möglich.
3. **Geht es primär um Stil/Format/Verhalten?** Ja → Fine-Tuning. Nein → RAG.
4. **Ist das Modell zu groß/teuer/lang­sam?** Ja → kleineres Modell + ggf. Fine-Tuning für die spezifische Aufgabe.
5. **Hast du saubere, kuratierte Trainings­daten (mindestens 1.000 Beispiele) für Fine-Tuning?** Wenn nicht, lass Fine-Tuning erstmal.

## Praktische Empfehlung für KMU

1. **Starte mit RAG** über ein Frontier-Modell (Claude / GPT-4 / Mistral Large)
2. **Miss die Performance** (Eval-Set mit echten Fragen, manuelles Scoring)
3. **Identifiziere systematische Schwächen** (Stil? Format? Wissen? Halluzinationen?)
4. **Wenn Stil/Format das Problem ist**: Fine-Tuning eines kleineren Modells erwägen
5. **Wenn Wissen das Problem ist**: RAG verbessern (besseres Chunking, Hybrid Search, Reranker)

In den meisten Projekten reicht Schritt 1+3+5 — Fine-Tuning kommt selten.

**Verwandt:**
- RAG-Tooling: `tech-stack/rag-and-vector.md`
- LLM-Wahl: `tech-stack/llms.md`
- Self-Hosting (für Fine-Tune-Deployment): `tech-stack/self-hosting.md`
