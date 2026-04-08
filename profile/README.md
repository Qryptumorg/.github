<p align="center">
  <img src="https://raw.githubusercontent.com/Qryptumorg/site/main/public/og-image.png" alt="Qryptum" width="100%" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Solidity-0.8.24-363636?style=flat-square&logo=solidity&logoColor=white" alt="Solidity" />
  <img src="https://img.shields.io/badge/TypeScript-5.7-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/Ethereum-L1-3C3C3D?style=flat-square&logo=ethereum&logoColor=white" alt="Ethereum" />
  <img src="https://img.shields.io/badge/Sepolia-testnet-00B4D8?style=flat-square" alt="Sepolia" />
  <img src="https://img.shields.io/badge/License-MIT-white?style=flat-square" alt="License" />
</p>

<p align="center">
  <a href="https://github.com/Qryptumorg/contracts/actions/workflows/test.yml"><img src="https://github.com/Qryptumorg/contracts/actions/workflows/test.yml/badge.svg" alt="contracts CI" /></a>
  <a href="https://github.com/Qryptumorg/app/actions/workflows/ci.yml"><img src="https://github.com/Qryptumorg/app/actions/workflows/ci.yml/badge.svg" alt="app CI" /></a>
  <a href="https://github.com/Qryptumorg/api/actions/workflows/ci.yml"><img src="https://github.com/Qryptumorg/api/actions/workflows/ci.yml/badge.svg" alt="api CI" /></a>
  <a href="https://github.com/Qryptumorg/db/actions/workflows/check.yml"><img src="https://github.com/Qryptumorg/db/actions/workflows/check.yml/badge.svg" alt="db CI" /></a>
</p>

---

# Qryptum

**Non-custodial, post-quantum ready token shielding protocol on Ethereum.**

Qryptum lets you shield any ERC-20 token into your own personal QRYPTANK vault.
Each QRYPTANK is a smart contract you alone control, protected by a 6-character
cryptographic vault proof. Shielded tokens become qTokens (e.g. qUSDT, qETH):
non-transferable at the contract level and impossible to move without both your
private key and your vault proof simultaneously.

No pool. No custody. No admin keys. Your tokens never leave your own vault contract.

## What makes it different

| Feature | Detail |
|---|---|
| Full self-custody | Your vault is your own smart contract. Qryptum holds nothing and has zero admin access. |
| Non-transferable qTokens | qToken transfer(), transferFrom(), and approve() always revert at contract level. Not just a UI restriction. |
| Commit-reveal transfers | Two-step transfer hides recipient and amount until reveal, protecting against front-running. |
| Vault proof protection | All vault operations require your cryptographic vault proof verified on-chain via keccak256. |
| Post-quantum design | Vault proof architecture designed with quantum-resistant access patterns in mind. |
| No shared pool | Every user gets one isolated vault contract for life. Funds are never commingled. |

## How shielding works

```mermaid
flowchart TD
    A[User Wallet] -->|1. shield and vault proof| B[QRYPTANK PersonalVault]
    B -->|2. pulls ERC-20 from wallet| B
    B -->|3. deploys qToken contract on first shield| C[qToken Contract e.g. qUSDT]
    C -->|4. mints qUSDT to user wallet| A
    A -->|qUSDT balance visible but non-transferable| A
```

## How shielded transfers work

```mermaid
flowchart LR
    A[Sender Wallet] -->|1. commitTransfer: submit hash| V[QRYPTANK Vault]
    V -->|2. wait 1 block| V
    A -->|3. revealTransfer: vault proof and nonce| V
    V -->|4. burn qToken from sender| V
    V -->|5. send raw ERC-20 directly| B[Recipient Wallet]
    B -->|receives USDT not qUSDT| B
```

The recipient always receives the original ERC-20 token, not qToken.
They can choose to shield it into their own QRYPTANK if they want.

## Security model

| Property | Detail |
|---|---|
| Vault model | Each user owns their personal vault contract. Qryptum holds nothing. |
| Admin access | Qryptum deployer has zero access to any user vault. No upgrade keys. No backdoors. |
| Vault proof | Raw proof sent in calldata, verified on-chain via keccak256. Safe because private key is still required. |
| Transfer safety | Requires private key and vault proof at the same time. Compromising one alone is not enough. |
| qToken design | Non-transferable permanently at Solidity level, not just in the UI. |

## Repositories

| Repo | Description | Stack |
|---|---|---|
| [contracts](https://github.com/Qryptumorg/contracts) | ShieldFactory, PersonalVault, ShieldToken | Solidity 0.8.24, Hardhat |
| [app](https://github.com/Qryptumorg/app) | Frontend dApp | React 19, Vite, wagmi, TypeScript |
| [api](https://github.com/Qryptumorg/api) | Backend REST API | Express, TypeScript, PostgreSQL |
| [db](https://github.com/Qryptumorg/db) | Database schema | Drizzle ORM, PostgreSQL |
| [site](https://github.com/Qryptumorg/site) | Landing page and docs | React 19, Vite, Tailwind CSS v4 |

## Stack

<p>
  <img src="https://img.shields.io/badge/Solidity-0.8.24-363636?style=for-the-badge&logo=solidity&logoColor=white" alt="Solidity" />
  <img src="https://img.shields.io/badge/Hardhat-yellow?style=for-the-badge&logo=ethereum&logoColor=white" alt="Hardhat" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite" />
  <img src="https://img.shields.io/badge/wagmi-3C3C3D?style=for-the-badge&logo=ethereum&logoColor=white" alt="wagmi" />
  <img src="https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Drizzle_ORM-C5F74F?style=for-the-badge&logoColor=black" alt="Drizzle" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind" />
</p>

## Status

Active development. Smart contracts complete with 83 passing test cases.
Sepolia testnet deployment in progress.

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-white.svg)](https://github.com/Qryptumorg/contracts/blob/main/LICENSE)

Copyright (c) 2026 [wei-zuan](https://github.com/wei-zuan). See [LICENSE](https://github.com/Qryptumorg/contracts/blob/main/LICENSE) for full terms.
