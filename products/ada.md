# Ada — das KI-Backoffice für den Mittelstand (Produkt von BlockBuilder UG)

Ada ist ein branchen-konfiguriertes KI-Backoffice auf europäischem Stack: Es entlastet Teams bei Posteingang, Schreibarbeit und Rechnungslauf — Entwürfe entstehen automatisch, die Freigabe bleibt immer beim Menschen (Human-in-the-Loop). Produktseite: https://block-builder.de/de/products/ada — Plattform-Übersicht mit allen Modulen pro Branche: https://block-builder.de/de/products/ada/plattform (Direktlink pro Branche via ?vertical=hausverwaltung|kanzlei|ecommerce|handwerk|systemtechnik).

## Kern-Plattform (in jedem Paket enthalten)

- **Posteingang & Triage:** Multi-Kanal-Posteingang (E-Mail/IMAP, Website-Chat, Telegram, API-Kanal), KI-Triage mit Antwortentwurf, Eskalation, Vier-Augen-Review, Anhänge mit Virenscan.
- **KI-Assistent:** systemweites Wissen über Akten, Vorgänge, Dokumente und Zahlen; Antworten mit Quellenangabe; stößt Aktionen an, die auf Freigabe warten; lernt aus Korrekturen (Freigabe-Queue); beantwortet auch Fragen zur Bedienung von Ada selbst.
- **Dokumenten-Studio:** KI-Entwurf und Umschreiben mit Track-Changes, Kontext aus der Akte mit Inline-Zitaten, Versionen und Wiederherstellung, DIN-5008-Layout, PDF-Export, Serienbrief, Vorlagen-Galerie, Rechtschreib-/Grammatikprüfung auf EU-Infrastruktur.
- **Akten & Dokumente:** Volltext- und Bedeutungssuche, KI-Texterkennung (OCR, EU) mit Konfidenz-Review, Inline-Vorschau, Archiv mit Nachvollziehbarkeit.
- **Vorlagen & Briefpapier:** eigenes Corporate Design, Layout-Baukasten, Branchen-Vorlagenpakete.
- **Team & Zusammenarbeit:** Kommentare mit @-Erwähnungen, Zuweisung und Auslastung, Benachrichtigungs-Center mit Desktop-Push.
- **Auswertungen & Kostenkontrolle:** Nutzungs-Dashboard, monatliches KI-Budget mit hartem Deckel.
- **EU-Souveränität & Sicherheit:** EU-Sprachmodelle (Mistral) mit technischer Modell-Richtlinien-Leitplanke, strikte Mandantentrennung (Row-Level-Security), Rollen und Rechte, EU-Hosting und EU-Speicher, Freigabe vor jedem Versand.

## Branchen (5 Ausprägungen, pro Branche konfiguriert)

- **Hausverwaltung/Mietverwaltung:** KI-Posteingang für Mieteranfragen, Handwerker-Koordination (Verzeichnis pro Gewerk, Notdienst, Beauftragung im Vorgang), Mieter/Objekte/Einheiten, Import aus dem Mietvertrag (OCR), Stapel-Import ganzer Bestände, Spam-Filter, 14 Branchen-Vorlagen.
- **Kanzlei & Rechtsberufe:** Kollisionsprüfung, Fristen-Board mit Vier-Augen-Prinzip, RDG-Kennzeichnung mit Review-Gate, Vertraulichkeitsstufen nach § 203 StGB mit Schutz-Gate, On-Premise-KI für berufsgeheimnisgeschützte Inhalte, Schriftsätze und Kanzlei-Vorlagen.
- **E-Commerce & Versandhandel (JTL-Wawi):** Bestell- und Versandstatus direkt aus JTL-Wawi (WISMO), Triage nach Shop-Kategorien (Versand, Retoure, Produktfrage, Reklamation, B2B), Auto-Antwort für Standardfälle mit Not-Aus und Protokoll, konfigurierbare Antwort-Persona, ERP-/Payment-Anbindung per API.
- **Handwerk (SHK & Gebäudetechnik):** Plantafel mit Drag-and-drop-Disposition, Einsatz-Regeln (Qualifikations-Gating, „Azubi nie allein"), Monteur-App als offline-fähige PWA mit QR-Scan, digitale Zeiterfassung mit Prüfpfad und ArbZG-Warnungen, Einsatzberichte mit Kundenunterschrift, Anlagen-Register mit QR-Etiketten, Wartungsverträge und Prüf-Planung (Heizung jährlich, DGUV V3), SLA und Stundenkontingente, Protokolle mit Grenzwert-Ampel, Artikelstamm und Angebots-Engine (DATANORM 4/5), KI-Disponent und KI-Stückliste.
- **IT- & Systemtechnik (Errichter, Systemhäuser):** derselbe Field-Service-Kern plus Wartung nach Norm (BMA 4×/Jahr nach DIN 14675, EMA je VdS-Grad, DGUV V3), Prüf- und Messprotokolle mit Betriebsbuch, DSGVO-Video-Paket-Generator als verkaufbares Deliverable, NIS2-gehärtete Inbetriebnahme-Doku, Kostenstellen/Abteilungen, Subunternehmer mit Compliance-Gate und Extern-Rolle, Anlagen-Tresor für Zugangsdaten, Großhandels-Anbindung (Open Masterdata, IDS-Connect, z. B. Rexel).

Weitere Branchen auf Anfrage — Ada wird pro Branche konfiguriert.

## Zubuchbare Bausteine (je Betrieb einzeln aktivierbar)

- **Telefon-Assistenz:** Ada nimmt Anrufe entgegen (Störungsannahme, Bestellstatus, Termine) auf europäischem Sprach-Stack, mit KI-Kennzeichnung und Übergabe an Menschen.
- **Sprachsteuerung in der App:** Push-to-Talk-Navigation und Aktionen mit Bestätigung, EU-Infrastruktur.
- **Rechnungen, Angebote & E-Rechnung:** alle Rechnungsarten, lückenlose Nummernkreise, Bau-Spezifika (§ 13b, § 48b), DATEV-Anschluss; E-Rechnung nach EN 16931 (XRechnung/ZUGFeRD), automatisch validiert.
- **Mahn- & Nachfass-Automatik:** Zahlungserinnerung, Mahnstufen 1–3, Angebots-Nachfassen — versendet nach Freigabe.
- **Auto-Antwort für Standardfälle:** vollautomatisch nach Einlernphase, mit Not-Aus (zuerst E-Commerce-Bestellstatus).
- **Kanal-Erweiterungen:** Telegram, Website-Chat, offener API-Kanal für ERP-/Payment-/Eigenanbindungen.
- **Frontier-KI mit Einwilligung:** leistungsstärkeres Modell fallweise zuschaltbar, klar gekennzeichnet, standardmäßig aus.
- **On-Premise-Betrieb:** komplette Plattform inklusive KI-Modellen auf eigener Infrastruktur.

## Datenschutz & EU-Souveränität

EU-Sprachmodelle (Mistral), Hosting in der EU, On-Premise-Option für sensible Inhalte, menschliche Freigabe vor jedem Versand. DSGVO-first konzipiert.

## Einführung

1. Demo- & Anforderungsgespräch → 2. Konfiguration & Anbindung (E-Mail, DATEV, JTL, …) → 3. Pilotbetrieb mit dem Team → 4. Produktivbetrieb & Ausbau. Typische Einführung: wenige Wochen, abhängig von den Anbindungen.

## Kosten

Ada ist kein Selbstbedienungs-Abo. Es gibt drei Kostenklassen — **Start** (kleines Team, ein Vertical, Cloud-EU), **Professional** (mehrere Nutzer, volle Kanal- und Rechnungs-Funktionen), **Enterprise On-Prem** (eigene Infrastruktur, individuelle Integrationen). Der konkrete Preis hängt von vier Faktoren ab: Nutzerzahl, Branche/Vertical, Feature-Umfang und Hosting (Cloud oder On-Premise) — die Einordnung erfolgt im Demo-Gespräch.

## Pilotprogramm / Design-Partner

BlockBuilder nimmt aktuell eine begrenzte Zahl an Pilotkunden auf, die Ada mitgestalten: bevorzugte Konditionen, direkter Draht zur Entwicklung, Einfluss auf die Roadmap. Ada ist bereits im Einsatz, u. a. bei einer bayerischen Hausverwaltung, einer Kanzlei und einem Onlinehändler (JTL).

## Demo

Demo-Termin direkt buchen: https://cal.block-builder.de/matthias/ada-demo — oder über die Produktseite https://block-builder.de/de/products/ada.
