# On-Premise vs Cloud AI — Entscheidungs­kriterien

Vier Achsen, klare Faustregeln. Beide Modelle haben legitime Use-Cases — pauschale Empfehlungen sind verdächtig.

## Die vier Achsen

### 1. Datenresidenz
| Anforderung | Empfehlung |
|---|---|
| Daten dürfen Gebäude nicht verlassen | On-Premise |
| Daten dürfen EU-Rechen­zentrum erreichen | Cloud-Hosted (Hetzner DE) oder On-Premise |
| Daten dürfen US-Cloud erreichen (mit DPA) | Cloud-API (OpenAI/Anthropic/Mistral) |

### 2. Volumen / Last
| Inference-Last | Empfehlung |
|---|---|
| Sporadisch, < 1 Mio Tokens/Monat | Cloud-API (Pay-per-Use) |
| Konstant, 1–50 Mio Tokens/Monat | Cloud-Hosted oder API mit Volumen­rabatt |
| Hoch, > 50 Mio Tokens/Monat, dauerhaft | On-Premise oder dedi­zierte Cloud-Instanz |

Break-Even-Faustregel: On-Premise-Hardware (~15.000 EUR) amortisiert sich gegen­über GPT-4-Klasse-API typischerweise nach 12–24 Monaten bei hoher Last.

### 3. Operations-Kapazität
| Team-Lage | Empfehlung |
|---|---|
| Kein eigenes IT-Team | Cloud-Hosted oder Cloud-API |
| Kleines IT-Team, kein GPU-Expertise | Cloud-Hosted (managed) oder mit unserem Service­paket |
| Eigenes Ops-Team mit Linux/Container-Erfahrung | On-Premise möglich |
| Eigenes Ops-Team mit GPU-Erfahrung | On-Premise klar machbar |

### 4. Modell-Qualität
| Anforderung | Empfehlung |
|---|---|
| Frontier-Reasoning (GPT-4o / Claude Opus-Klasse) | Cloud-API |
| Solide Qualität, deutsche Sprache | Mistral (EU-Cloud) oder Llama 70B+ (Self-Hosted) |
| Spezialisierte Modelle (Embedding, OCR, Voice) | Mix aus Cloud-API + Self-Hosted |

## Drei archetypische Szenarien

### Szenario A: Mittelständler, 50 MA, RAG über interne Verträge
- Datenresidenz: EU-Cloud OK
- Volumen: moderat (alle Mitarbeiter:innen haben Zugriff, aber Last verteilt)
- Ops: kleines IT-Team
- Modell: solide, Sprache deutsch

→ **Cloud-Hosted bei Hetzner mit Mistral Large** oder pgvector + OpenAI/Anthropic API mit DPA.

### Szenario B: Verteidigungs-Zulieferer, sensible Konstruktions­daten
- Datenresidenz: hart on-premise
- Volumen: niedrig bis moderat
- Ops: vorhanden
- Modell: solide

→ **On-Premise mit Llama 3 70B auf eigener NVIDIA-Hardware.** Investitions­schwelle ~15.000 EUR, ~300 EUR/Monat laufend.

### Szenario C: Solo-Berater:in, will KI im Alltag nutzen
- Datenresidenz: nicht hart
- Volumen: niedrig
- Ops: keine
- Modell: Frontier hilfreich

→ **Cloud-API (Claude / GPT-4)** + DSGVO-Abklärung via DPA. Self-Hosting wäre Overkill.

## Häufige Fehler

### "Wir wollen On-Premise, weil DSGVO"
DSGVO ist mit DPA + EU-Region oft sauber lösbar. On-Premise ist überlegen bei harten Daten­residenz-Anforderungen — aber DSGVO an sich verlangt es nicht.

### "Cloud-API ist immer billiger"
Bei hoher konstanter Last (>50 Mio Tokens/Monat) wird Self-Hosting günstiger. Bei 1-Mann-Show ist API immer günstiger.

### "Wir kaufen mal eine GPU"
Ohne Setup-Plan, Ops-Konzept und Modell-Wahl wird die GPU schnell zum Ausstellungs­stück. On-Premise braucht ein Operating-Konzept.

## Default-Empfehlungen

| Profil | Default |
|---|---|
| Solo / Mikro­unternehmen | Cloud-API |
| KMU 10–50 MA, kein IT-Team | Cloud-Hosted (Hetzner DE) |
| KMU 50–250 MA mit IT-Team | Cloud-Hosted oder On-Premise (je nach Compliance) |
| Mittel­ständler 250+ MA mit Compliance-Druck | On-Premise mit Cloud-API als Fallback |

**Verwandt:**
- On-Premise-Service: `services/on-premise-ai.md`
- Datenresidenz: `compliance/data-residency.md`
- Infrastruktur: `tech-stack/infrastructure.md`
