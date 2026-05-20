# Persönlicher KI-Assistent für einen Immobilien-Verwalter

## Kunde (anonymisiert)

Inhabergeführter mittelständischer Immobilien-Verwalter mit eigenem Portfolio in Süddeutschland.

## Was wir gebaut haben

Vollständig souveräner KI-Assistent als Mehrkanal-Personal-Agent — auf **eigenem ARM64-Server** beim Kunden. Funktionsumfang:

- **Multi-Channel-Eingang**: Telegram (primär), E-Mail, Sprachein-/ausgabe
- **GoBD-konforme Rechnungserstellung** mit automatischer Anzahlungsverrechnung
- **Schadensmeldungen** mit Dringlichkeitsbewertung und Triage
- **Besichtigungsplanung** inkl. Terminkoordination mit Interessenten
- **Mietervorlagen** (Anschreiben, Mahnungen, Standardkommunikation)
- **Bautagebuch** aus Sprachmemos automatisch transkribiert und strukturiert
- **Fahrtenbuch** mit automatischer Klassifikation
- **Visitenkarten-OCR** für Kontakt-Import
- **Eigene 2FA-/Captcha-Workflows** via Browser-in-the-Cloud (Apache Guacamole + Xvfb)

## Stack

Hermes Agent (Nous Research), MiniMax LLM via OpenRouter, FastAPI + Python 3.12, SQLite (WAL) + WeasyPrint (DIN-5008-PDFs), Traefik v3, Telegram Bot API, Himalaya + Microsoft 365 OAuth2, faster-whisper STT, Piper TTS, Apache Guacamole + Xvfb, Hetzner ARM64 (CAX31).

## Warum dieser Stack

- **Hermes Agent (Open Source)** — keine Lock-in-Abhängigkeit, läuft komplett auf Kunden-Hardware
- **MiniMax via OpenRouter** — gute Qualität-Kosten-Ratio, einfacher Anbieter-Wechsel
- **SQLite (WAL)** — für Single-User-Szenario ideal, kein Datenbank-Server-Overhead
- **WeasyPrint** — DIN-5008-konforme PDFs ohne externe PDF-Dienste
- **Hetzner ARM64 (CAX31)** — kostengünstig, EU-Hosting, energieeffizient
- **Apache Guacamole** — elegante Lösung für 2FA-/Captcha-Hürden bei externen Portalen

## Status

In Produktion seit 02/2026. Monatliches Servicepaket für Betrieb und Weiterentwicklung.

## Was dieses Projekt zeigt

- **Personal-Agent** für Einzelnutzer:innen ist ein realer, lieferbarer Use-Case — nicht nur Vision
- **Multi-Channel-Eingang** ist Pflicht, nicht Kür (E-Mail UND Telegram UND Sprache)
- **GoBD- und DSGVO-Konformität** lassen sich mit Self-Hosting sauber lösen
- **Browser-in-the-Cloud** ist die ehrliche Antwort für Portale, die noch keine API anbieten

**Verwandt:**
- KI-Agenten-Service: `services/ai-agents.md`
- Self-Hosting: `tech-stack/self-hosting.md`
- Mehr dazu: https://block-builder.de/de/projekte
