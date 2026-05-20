# KI-Editor-Erweiterung für einen juristischen SaaS-Anbieter

## Kunde (anonymisiert)

Mittelständischer Anbieter juristisch-administrativer SaaS-Lösungen.

## Was wir gebaut haben

Eine produktionsreife TipTap-basierte KI-Editor-Komponente, direkt in die bestehende Rich-Text-Oberfläche eingebettet. Funktionsumfang:

- **13 KI-Aktionen** im Editor: Umformulieren, Kürzen, Vereinfachen, Formalisieren, Diktat-zu-Prosa, Zusammenfassen u.a.
- **Ghost-Text-Vorschläge** und Smart Completion direkt im Schreibfluss
- **LGPL-sichere Grammatik- und Rechtschreibprüfung** (lizenzkonform für kommerzielle SaaS-Nutzung)
- **Mandantenfähiges Backend** mit Bearer-Token-Auth
- **Server-Sent-Events-Streaming** für niedrige Latenz
- **Konfigurierbarer Prompt-Loader** pro Aktion — Kunde kann Prompts ohne Deployment anpassen

## Stack

TypeScript, Vue 3, TipTap (ProseMirror), Fastify, Mistral AI, LanguageTool, SSE, Caddy + Let's Encrypt, Hetzner CPX32, Docker, Vitest.

## Warum dieser Stack

- **TipTap (ProseMirror)** — der Kunde hatte bereits einen TipTap-Editor, saubere Integration ohne UI-Bruch
- **Mistral AI** — solide Qualität, EU-Anbieter (Frankreich), DSGVO-freundlich
- **LanguageTool** — Open Source mit LGPL, in juristischem Kontext erprobt
- **Fastify + SSE** — minimale Latenz für Streaming-Antworten direkt in den Editor
- **Hetzner CPX32** — EU-Hosting (Deutschland), kostengünstig für mittelständische SaaS

## Status

Milestone 1 abgenommen 05/2026. Milestone 2 in Arbeit.

## Was dieses Projekt zeigt

- KI-Funktionalität lässt sich sauber in **bestehende** Rich-Text-UIs integrieren, ohne dass die App "wie ein KI-Tool" aussieht
- **Lizenz-Sorgfalt** bei OSS-Komponenten (LGPL/AGPL/GPL) ist in B2B-SaaS keine Optionalität
- **Streaming-First-Architektur** macht den Unterschied zwischen "fühlt sich smart an" und "wir warten auf eine Antwort"

**Verwandt:**
- Service-Seite: `services/software-development.md`
- LLM-Wahl: `tech-stack/llms.md`
- Mehr dazu: https://block-builder.de/de/projekte
