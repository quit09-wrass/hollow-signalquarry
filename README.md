# Hollow Signalquarry

Hollow Signalquarry is a compact, browser-first Base inspection workspace built for fast confirmation of network identity and convenient read-only visibility into public chain data. It focuses on repeatable validation with direct Basescan references.

---

## Base network context

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

The application targets Base explicitly and validates Base-compatible chainIds before presenting results.

---

## Tooling and dependencies

This repository intentionally mixes Base and Coinbase ecosystem tooling:

- Coinbase Wallet SDK for EIP-1193 wallet connectivity  
- OnchainKit references for Base-aligned primitives and account abstraction context  
- viem for typed, efficient read-only RPC requests  
- Direct Git dependencies for multiple Base and Coinbase repositories  

---

## Installation and execution

Install dependencies using Node.js.  
Serve the project with a modern frontend dev server and open it in a browser.

Expected outcome:
- Active network and chainId shown (8453 or 84532)  
- Wallet session details displayed after connection  
- Read-only balance, block, gas, and ERC-20 data available  
- Basescan links printed for external verification  

---

## Capabilities overview

Hollow Signalquarry exposes a deliberately small surface:

- Wallet connection and chainId verification  
- ETH balance reads for any address  
- Latest block snapshot with timestamp and gas fields  
- RPC pulse check (chainId, height, gas price)  
- ERC-20 metadata and holder balance reads  
- Basescan URLs for block, token, and address inspection  

No transactions are created, signed, or broadcast.

---

## Repository layout

- app/hollow-signalquarry.ts  
  Browser script rendering a minimal UI for Base read-only inspection.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - inheritance_contract.sol — inherits logic and state from a parent contract 
  - ERC721.sol — contract that supports transfers and approvals
   
- config/networks.json  
  Static Base network configuration (chainIds, RPC endpoints, explorers).

- package.json  
  Dependency manifest referencing Coinbase SDKs and multiple Base + Coinbase repositories.

- README.md  
  Technical documentation and deployment records.

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author contacts

GitHub: https://github.com/quit09-wrass

Email: quit09.wrasse@icloud.com  

X: https://x.com/cruela_boy 

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract inheritance_contract.sol address:  
0x0ec7ca9596b0b7e9eb3737753ac8e68a246d02d9 

Deployment and verification:
- https://sepolia.basescan.org/address/0x0ec7ca9596b0b7e9eb3737753ac8e68a246d02d9 
- https://sepolia.basescan.org/0x0ec7ca9596b0b7e9eb3737753ac8e68a246d02d9/0#code  

Contract ERC721.sol address:  
0xa117a82a4dbe1eaefa4a1263e66d46586fd296cf

Deployment and verification:
- https://sepolia.basescan.org/address/0xa117a82a4dbe1eaefa4a1263e66d46586fd296cf
- https://sepolia.basescan.org/0xa117a82a4dbe1eaefa4a1263e66d46586fd296cf/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
