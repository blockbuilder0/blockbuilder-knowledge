# Web3-Namensdienst auf Ethereum (ENS-ähnlich)

## Kunde (anonymisiert)

Etablierter deutscher IT-Systemintegrator (~250 Mitarbeitende), F&E im Bereich dezentrale Identität.

## Was wir gebaut haben

End-to-End-Prototyp eines ENS-ähnlichen Namensdienstes auf Ethereum. Kernkomponenten:

- **TLD-NFT-Smart-Contracts** mit On-Chain-Subdomain- und DNS-Record-Verwaltung (A/AAAA)
- **Marketplace-Smart-Contract** für Domain-Handel (Listings, Bids, Transfers)
- **Nativer Go-DNS-Resolver**, der reale DNS-Anfragen via RPC gegen Ethereum auflöst
- **The-Graph-Subgraph** (AssemblyScript) für indexierte On-Chain-Events
- **Chrome-Extension** als Browser-Plugin (Manifest V3) für direkten Zugriff aus dem Browser

## Stack

Solidity, Hardhat, Ethereum (Sepolia-Testnet), The Graph Protocol (AssemblyScript), Go (nativer DNS-Stack + go-ethereum), JavaScript (Chrome Extension Manifest V3), Alchemy RPC, PlantUML / Mermaid für Architektur-Doku.

## Warum dieser Stack

- **Solidity + Hardhat** — Industriestandard für EVM-Contracts, gutes Tooling für Testing und Deployment
- **The Graph Protocol** — vermeidet teure On-Chain-Queries durch off-chain-indexierte Events
- **Go-DNS-Resolver** — native Performance für DNS-Auflösung, sauber integrierbar in bestehende DNS-Infrastruktur
- **Chrome Extension Manifest V3** — zukunftssicher gegenüber Manifest-V2-Deprecation
- **Sepolia-Testnet** — realistische Testumgebung ohne Mainnet-Gas-Kosten in der F&E-Phase

## Status

Funktionsfähiger Prototyp, deployed auf Sepolia (Projekt abgeschlossen 2023).

## Was dieses Projekt zeigt

- **End-to-End-Web3-Stack** kann in der F&E-Phase sauber gegen Testnet entwickelt werden
- **Off-Chain-Indexierung** (The Graph) ist Pflicht für jede realistische dApp — On-Chain-Queries skalieren nicht
- **Bridges zur klassischen Web-Welt** (DNS-Resolver, Browser-Extension) sind oft der schwierigere Teil als die Contracts selbst
- **Blockchain-Projekte mit klarem Use-Case** (dezentrale Identität, verifizierbare Records) sind weiterhin lieferbar — der Skepsis-Filter aus `services/blockchain.md` filtert die Mehrheit der Anfragen aber zu Recht aus

**Verwandt:**
- Blockchain-Service: `services/blockchain.md`
- Entscheidung Blockchain vs AI: `decision-matrices/blockchain-vs-ai.md`
- Mehr dazu: https://block-builder.de/de/projekte
