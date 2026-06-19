# ashlNc Backdoor — Security Advisory

**GHSA-hxf3-5h5r-xr7c | CVE: Pending (GitHub CNA)**

> Multi-layered Node.js backdoor with decentralized C2 via Solana blockchain memos and Kademlia DHT. A novel zero-day backdoor discovered on a Windows system — no prior public reporting exists.

## Overview

This repository documents the full reverse engineering of the **ashlNc** backdoor, including:

- **3 encryption layers**: Base64 + AES-256-CBC + 747KB Webpack bundle
- **Decentralized C2**: Solana blockchain memos + Kademlia DHT + Socket.IO — no hardcoded IPs
- **Capabilities**: Credential theft, crypto wallet draining (9 Solana RPC nodes), RCE, file exfiltration, self-healing persistence
- **Additional infections discovered**: Nemotrix adware + Chrome extension jucku (keylogger, clipboard capture, Bybit cookie theft)

## Advisory Status

| Field | Value |
|-------|-------|
| GHSA ID | GHSA-hxf3-5h5r-xr7c |
| State | Published |
| CVE ID | Pending (requested via GitHub CNA) |
| Severity | CVSS 9.8 (Critical) |
| Discovered | 2026-04-08 |
| Remediated | 2026-06-19 |

## Key Indicators (IOCs)

| Type | Value |
|------|-------|
| Solana Wallet (C2) | BjVeAjPrSKFiingBn4vZvghsGj9KCE8AJVtbc9S8o8SC |
| DHT Public Key | ea1b4260a83348243387d6cdfda3cd287e323958 |
| Registry Key | vUVlUXNH |
| Chrome Extension ID | haookbehcedinkhoekmkbjopifpheimj |
| Malware Paths | %APPDATA%\ashlNc\, %LOCALAPPDATA%\ashlNc\, %APPDATA%\_node_x86\ |

## Infection Vector

**npm supply chain attack** — a trojanized Solid.js/Vite project contained malicious postinstall scripts that deployed the backdoor when `npm install` was executed.

## Reports

Full bilingual report (English + Arabic) with MITRE ATT&CK mapping, prevention guide, and remediation:

- [`report.html`](./report.html) — Combined bilingual report

## Remediation

The system has been fully cleaned. See the report for complete prevention guidance.

## Links

- [GitHub Advisory](https://github.com/Haitham8888/ashlNc-backdoor/security/advisories/GHSA-hxf3-5h5r-xr7c)
- [Solana Explorer — C2 Wallet](https://solscan.io/account/BjVeAjPrSKFiingBn4vZvghsGj9KCE8AJVtbc9S8o8SC)
