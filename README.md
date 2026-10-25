# 🪙 Eidos Tokenization Engine (`compilatorum/eidos-tokenization`)

> **Sovereign Endogenous Asset & IP Tokenization System on Solana (`SPL Token-2022` + `EidosManifest v1.0`)**  
> Extracted as a standalone modular repository within the **Compilatorum** ecosystem, composing seamlessly with **ValueCurator** (`smp-sandramariapereira/valuecurator`).

---

## 🏛️ Architectural Overview

This repository encapsulates the **Endogenous Asset Factory** for minting verifiable intellectual property, AI constructs, formal glyphs, and research artifacts on **Solana Devnet / Mainnet** using **SPL Token-2022 (Token Extensions)**:

1. 📜 **`EidosManifest v1.0` (`schemas/ResearchNFTManifest.schema.json`)**:
   * Formal JSON Schema separating cryptographic token ownership from intellectual property licensing (`SPDX`, `ai_agent_access: MACHINE_PAYABLE`, `royalty_bps`, and SHA-256 genealogy).
2. 🦀 **Anchor CPI Mint Instruction (`programs/eidos-mint-engine/src/mint_research_asset.rs`)**:
   * Enforces **Program Derived Address (`Node PDA`)** exclusive `MintAuthority` (`seeds = [b"node", owner.key().as_ref(), &[node.bump]]`), ensuring zero human or raw-key exposure during asset issuance.
3. ⚡ **TypeScript Devnet Minting Suite (`src/mint-research-nft.ts`)**:
   * End-to-end script and SDK to derive the `Vault PDA`, initialize the `SPL Token-2022` Mint account, create the recipient Associated Token Account (ATA), and execute atomic minting with Solscan verification links.

---

## 📂 Repository Structure

```text
eidos-tokenization/
├── programs/
│   └── eidos-mint-engine/
│       └── src/
│           └── mint_research_asset.rs        # Rust/Anchor SPL Token-2022 CPI mint handler
├── schemas/
│   ├── ResearchNFTManifest.schema.json       # EidosManifest v1.0 JSON Schema (Draft 2020-12)
│   └── sample-research-nft.manifest.json     # Concrete manifest for Neuro-Symbolic Oracle R-NFT
├── src/
│   └── mint-research-nft.ts                  # TypeScript Devnet Token-2022 minting runner
├── docs/
│   ├── EXPERIMENTO_MINTAGEM_RESEARCH_NFT_TOKEN2022_E_COMPARATIVO_DEVNET.md
│   ├── PITCH_DECK_SUBPROJETO_DEVNET_E2E_TOKENIZATION.md
│   └── PITCH_DECK_SUBPROJETO_DEVNET_E2E_TOKENIZATION.html
├── experiment-output.json                    # Verified Devnet minting telemetry artifact
├── package.json
└── tsconfig.json
```
