# Decentralized Identity Verification System

This project is a blockchain-based **decentralized identity** platform that lets individuals issue, manage, and revoke verifiable identity credentials using an Identity Digital Wallet, while third parties securely verify those credentials through a dedicated Verification Interface on an Ethereum-compatible network.

---

## Overview
 
The system uses smart contracts deployed on the Ethereum Virtual Machine (EVM) to anchor credential state on-chain, while business logic and user interfaces run off-chain for flexibility and privacy-preserving data handling.
It supports the full identity credential lifecycle (issuance, verification, revocation) with a focus on user control over sensitive data and seamless verifier workflows.

<img width="4508" height="2080" alt="image" src="https://github.com/user-attachments/assets/8e7867b5-655e-4457-8a35-0ffa7bc8a0de" />

---   

## Architecture  

- **Smart Contracts (Solidity + Truffle)**  
  Implement identity credential operations (issue, verify, revoke, query) and are deployed to a local Ganache-powered Ethereum network for development and testing.

- **Backend (Node.js, MVC + Web3.js)**  
  Acts as the business logic layer, connecting the React frontend to the Ethereum network, orchestrating identity flows, and exposing APIs for credential operations.

- **Frontend (React.js)**  
  Provides the Identity Digital Wallet UI and Verification Interface, enabling MetaMask connection, credential management, and verification screens for third parties.

- **Ganache Module (Shell scripts)**  
  Automates local blockchain setup, reset, and startup, including mnemonic generation and test accounts on `http://127.0.0.1:8545'.

---

## Project Structure

- `smart_contracts/` – Truffle project containing the Identity smart contract, migrations, and tests (`truffle compile`, `truffle migrate --reset`, `truffle test`).
- `backend/` – Node.js MVC server integrating with Web3.js, using environment variables like `GANACHE_RPC_URL` and `DEPLOYED_CONTRACT_ADDRESS`, and exposing APIs to the frontend.
- `frontend/` – React application for wallet connection, credential issuance, revocation, and viewing identity credentials, typically served at `http://localhost:3000`. 
- `ganache/` – Shell scripts (`config-ganache.sh`, `start-ganache.sh`) to initialize and manage the local Ganache blockchain, driven by a mnemonic stored in `.env`.
- `resources/` – Diagrams for the high-level system architecture and smart contract design.[page:0]

---

## Prerequisites

- Node.js and npm  
- React.js  
- Solidity and Truffle Suite  
- Ganache (CLI) for local EVM  
- Web3.js  
- MetaMask browser extension

---

## Roadmap

### High Priority

- Redefine the credential issuance form with stronger validation and more relevant fields.  
- Integrate identity document processing for richer verification.

### Medium Priority

- Build a dedicated Verification Interface for third-party validation requests.  
- Implement an authentication layer for the Verification Interface.  
- Extend unit and integration tests across all components with higher coverage.  
- Improve performance across smart contracts, backend, and frontend.  
- Add per-user secret keys for controlled credential access.

### Low Priority

- Support multiple wallet providers beyond MetaMask.  
- Introduce age-based identity handling (e.g., special flows for users under 18).



