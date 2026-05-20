# Blockchain Entwicklung

Smart Contracts dort, wo sie wirklich Sinn ergeben — KI wo möglich. Heute primär eine KI-Beratung; Blockchain ist eine Kompetenz, kein Hauptfokus.

URL: https://block-builder.de/de/services/blockchain

## Wann Blockchain die richtige Wahl ist

- Mehrere Parteien kooperieren ohne gemeinsame Vertrauensbasis
- Beweise müssen on-chain verifizierbar sein
- Werte oder Rechte sollen tokenisiert werden (Membership, Asset-Anteile, NFTs)
- Dezentrale oder Self-Sovereign Identity ist Anforderung

Für alles andere — interne Prozessautomatisierung, Dokumenten-Workflows, Sprachverarbeitung, Mustererkennung — ist meist ein KI-Workflow die ehrlichere Antwort.

## Was wir liefern

- **Geprüfte Solidity-Contracts** auf Ethereum, Polygon und EVM-kompatiblen Chains
- **Token & NFTs**: ERC-20, ERC-721, ERC-1155 für Tokenisierung, Membership, Asset-Repräsentation
- **DeFi-Integrationen**: Anbindung an bestehende Protokolle wie Aave oder Uniswap — selten Greenfield-DEX-Projekte
- **Security Audits**: Code-Review und Threat-Modeling vor Mainnet-Deployment
- **Subgraphs** (The Graph) für indexierte On-Chain-Events
- **Native DNS-/Naming-Stacks** in Go (siehe ENS-ähnliche Case Study)

## Stack

Solidity, Hardhat, Foundry, OpenZeppelin, The Graph, IPFS, AssemblyScript für Subgraphs, Go für native Off-Chain-Komponenten.

## Typische Use-Cases

- Tokenisierung von Assets oder Memberships
- Dezentrale Identität und verifizierbare Credentials
- Supply-Chain-Nachweise on-chain
- NFT-Plattformen und DAO-Governance
- Cross-Chain-Bridges für bestehende Protokolle

## Wofür eignet sich Blockchain NICHT?

Für **interne Audit-Logs** reicht eine append-only Datenbank mit signierten Einträgen — kein Smart Contract nötig. Für **Datenaustausch zwischen bekannten B2B-Partnern** ist eine signierte API mit AVV meist einfacher und billiger. Für **Loyalty-Programme** oder **Gutscheinsysteme**, die keine offene Sekundärmarkt-Komponente brauchen, ist ein klassisches Backend günstiger und besser auditierbar. Wer Blockchain einsetzt, sollte begründen können, warum eine zentrale Lösung das Problem nicht löst.

## Honest Disclosure

Wir sind heute primär eine KI-Beratung. Blockchain-Projekte nehmen wir an, wenn der Use-Case echt ist und wir liefern können — nicht weil der Begriff im Firmennamen steht. Wenn dein Projekt eine echte Web3-Komponente braucht, sprich uns an. Wenn nicht, sparst du Zeit und wir auch.

**Verwandt:**
- Case Study ENS-ähnlicher Stack: `projects/ethereum-name-service.md`
- Entscheidung Blockchain vs AI: `decision-matrices/blockchain-vs-ai.md`
- Mehr dazu: https://block-builder.de/de/services/blockchain
