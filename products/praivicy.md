# prAIvicy — Privacy-Plattform für DSGVO-freundliche KI-Nutzung (Beta)

prAIvicy ist das Software-Produkt der BlockBuilder UG: eine Privacy-Plattform, die personenbezogene Daten automatisch anonymisiert, bevor sie an KI-Modelle wie ChatGPT, Claude, Mistral oder Gemini übermittelt werden — und die Originaldaten in der Antwort wieder einsetzt. Anonymisierung und Hosting laufen vollständig in Deutschland.

URL: https://block-builder.de/de/products/praivicy
Status: Beta — die Warteliste ist offen, Einladungen erfolgen gestaffelt in Wellen.
Beta-Anmeldung: über das Formular auf der Produktseite (E-Mail genügt).

## Die zwei Wege, prAIvicy zu nutzen

1. **KI-Assistent für Teams (ohne Code):** Ein fertiger, browserbasierter KI-Assistent. Einloggen, Berufsgruppe wählen, arbeiten. Chat mit Dokumenten, Audio und Bildern — jede Nachricht wird anonymisiert, bevor sie das KI-Modell erreicht.
2. **API für Entwickler:** OpenAI-/Anthropic-kompatibler Endpoint. Base-URL der bestehenden Integration tauschen — eine Zeile Konfiguration. Die Anwendung schickt danach nur noch anonymisierte Daten an die Modelle.

## Kernfunktionen

- **Deutsch-zuerst-Erkennung:** Über 30 Datentypen, optimiert für deutsche Formate (IBAN, Steuer-ID, USt-IdNr, Kfz-Kennzeichen, Adressen, Namen), insgesamt 17 europäische Sprachen.
- **Reversible Anonymisierung:** Personenbezogene Daten werden durch Platzhalter ersetzt (z.B. [PERSON_1]); die Zuordnung existiert nur für die Dauer der einzelnen Anfrage und wird nicht dauerhaft gespeichert.
- **Mehr als Text:** Auch PDF- und Office-Dokumente, Tabellen, Audio (Transkription) und Bilder (OCR, Gesichts- und Unterschriften-Schwärzung) werden anonymisiert.
- **Secrets-Erkennung:** Erkennt auch API-Keys, Zugangsdaten und private Schlüssel — nicht nur personenbezogene Daten.
- **Ein Endpoint, alle Modelle:** OpenAI, Anthropic, Mistral, Google und mehr über eine API; Modellwechsel ohne Code-Änderung.
- **Bring Your Own Key (BYOK):** Kunden nutzen ihre eigenen KI-Anbieter-Accounts; Schlüssel werden ausschließlich verschlüsselt gespeichert.
- **Audit-Log und Dashboard:** Nachvollziehbar, welche Datentypen wann anonymisiert wurden — vorzeigbar gegenüber Datenschutzbeauftragten.

## Berufsspezifischer KI-Assistent

Der integrierte Assistent passt Arbeitsweise, Quick Actions und Wissensquellen an die Berufsgruppe an. Acht Berufsprofile zum Start: Anwälte, Steuerberater, Ärzte, Psychotherapeuten, Wirtschaftsprüfer, Notare, Architekten, Apotheker — besonders wertvoll für Berufe, die mit vertraulichen Mandanten- und Patientendaten arbeiten.

- **Zitierfähige Rechtsdatenbank:** Deutsche Gesetze (BGB, HGB, ZPO, StGB, GG u.a.) direkt im Chat; Paragraphen werden aus der Datenbank zitiert und verlinkt, mit Schutz gegen erfundene Fundstellen. Kein Ersatz für Rechtsberatung.
- **Quick Actions je Beruf:** z.B. für Anwälte Klauselanalyse, Schriftsatz-Gerüst, Fristen prüfen, Sachverhalt strukturieren.
- **Canvas für Entwürfe:** Verträge, Schriftsätze, Briefe und Gutachten entstehen in einem editierbaren Dokument neben dem Chat — versioniert und exportierbar.
- **Teams, Akten & Budgets:** Mandate/Projekte als Akten organisieren, Unterhaltungen im Team teilen, Kosten pro Mitglied steuern.

## Beta-Konditionen

- 3 Monate kostenlos für Beta-Teilnehmer
- Direkter Draht zum Entwicklerteam, Feature-Wünsche werden priorisiert
- Beta-Vereinbarung inklusive Auftragsverarbeitungsvertrag (AVV)
- Nach der Beta sind Pläne ab 49 € pro Monat geplant

## Häufige Fragen

**Muss ich meinen Code umbauen?** Nein — API-kompatibel zu OpenAI und Anthropic; in der Regel genügt der Tausch der Base-URL. Ohne eigene Integration nutzt man einfach den Assistenten im Browser.

**Wo werden Daten verarbeitet?** Die Anonymisierung läuft auf Servern in Deutschland, bevor etwas die EU verlässt. Die Zuordnung Originaldaten↔Platzhalter wird nicht dauerhaft gespeichert.

**Wer steckt dahinter?** prAIvicy ist ein Produkt der BlockBuilder UG (München) — entstanden aus der Beratungspraxis für DSGVO-freundliche KI-Einführung im Mittelstand.

**Ersetzt prAIvicy Datenschutz-Beratung?** Nein. prAIvicy ist eine technische Maßnahme im Sinne von Privacy by Design (Art. 25 DSGVO) — ein Baustein der Compliance, kein Ersatz für die rechtliche Bewertung.
