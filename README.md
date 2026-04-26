# Regulated Digital Access Tokens

## Project Overview
This project implements a custom **ERC-721 smart contract** that enforces secondary market rules directly on-chain.

Unlike standard Web3 digital assets, this protocol mathematically prevents price gouging (scalping) and ensures original creators are continually compensated without relying on centralized marketplaces.

**Core Mechanics:**
- Standard peer-to-peer transfers are disabled.
- All resales are forced through the contract's internal marketplace.
- Resale prices are strictly capped at **110%** of the original mint price.
- A **10% royalty** is automatically routed to the original creator on every successful resale.

---

## Tech Stack
- **Smart Contracts:** Solidity, OpenZeppelin
- **Testing & Deployment:** Hardhat, Sepolia Testnet
- **Frontend:** React.js, Tailwind CSS
- **Web3 Integration:** Ethers.js

---

## Repository Structure

```bash
├── contracts/                  # Smart contract source files (.sol)
├── test/                       # Hardhat test suites
├── scripts/                    # Deployment scripts for local/Sepolia
├── frontend/
│   ├── public/                 # Static assets (index.html, icons, etc.)
│   └── src/
│       ├── blockchain/         # Ethers.js integration and custom hooks
│       ├── components/         # React UI components
│       └── App.jsx             # Main application entry point
└── docs/                       # Architecture notes and AI prompts
```

---

## Shared API Blueprint

To ensure parallel AI code generation without integration conflicts, all team members must adhere to these exact function signatures.

### Smart Contract Functions (Solidity)
```solidity
function mintToken() external payable;
function listToken(uint256 tokenId, uint256 price) external;
function buyToken(uint256 tokenId) external payable;
function cancelListing(uint256 tokenId) external;
function getListing(uint256 tokenId) external view returns (uint256 price, address seller);
```

### Frontend Integration Hooks (Ethers.js)
```javascript
connectWallet()
mintToken()
listToken(tokenId, price)
buyToken(tokenId)
cancelListing(tokenId)
getMarketplaceListings()
getOwnedTokens(address)
```

---

## Team Ownership & Domains

To prevent AI-generated code from overwriting parallel work, responsibilities are strictly siloed.

* **Protocol Architect:** Owns `/contracts` and `/test`. Responsible for Solidity logic, openZeppelin overrides, and rigorous edge-case testing via Hardhat.
* **Bridge Engineer:** Owns `/frontend/src/blockchain`. Responsible for Ethers.js integration, reading/writing blockchain state, and handling wallet connection/transaction lifecycles.
* **Frontend Visionary:** Owns `/frontend/src/components`. Responsible for the visual React.js interface, user experience, and styling.

---

## Rules for Collaboration
* **Stay in your lane:** Only modify files within your assigned directory.
* **Respect the API:** Do not rename shared functions or alter the expected arguments without a full team discussion.
* **Main is sacred:** The `main` branch must always remain stable and deployable.
* **Review process:** Always open a Pull Request before merging your AI-generated code. 

---

## Project Goal
Deliver a working decentralized application (dApp) that successfully demonstrates:
1. Anti-scalping policy enforcement.
2. Automated royalty routing.
3. Deterministic economic rules strictly managed on-chain.