# Regulated Digital Access Tokens

## Project Overview
This project implements a custom ERC-721 smart contract that enforces secondary market rules directly on-chain.

Unlike standard NFTs:
- peer-to-peer transfers are disabled
- all resales must happen through the contract marketplace
- resale price is capped at 110% of mint price
- 10% royalty automatically goes to the original creator

## Tech Stack
- Solidity
- OpenZeppelin
- Hardhat
- React
- Ethers.js
- Sepolia Testnet

---

## Repository Structure

contracts/ -> smart contracts
test/ -> hardhat tests
scripts/ -> deployment scripts
frontend/src/blockchain/ -> ethers integration
frontend/src/components/ -> UI components
docs/ -> architecture and research notes

---

## Shared Contract API

### Smart Contract Functions

mintToken()

listToken(uint256 tokenId, uint256 price)

buyToken(uint256 tokenId)

cancelListing(uint256 tokenId)

getListing(uint256 tokenId)

---

## Frontend Integration API

connectWallet()

mintToken()

listToken(tokenId, price)

buyToken(tokenId)

cancelListing(tokenId)

getMarketplaceListings()

getOwnedTokens(address)

---

## Team Ownership

### Protocol Architect
Owns:
contracts/
test/

### Bridge Engineer
Owns:
frontend/src/blockchain/

### Frontend Visionary
Owns:
frontend/src/components/

---

## Rules for Collaboration

1. Only modify files in your assigned folder
2. Do not rename shared functions
3. Do not change API without discussion
4. Open Pull Request before merging
5. main branch stays stable

---

## Project Goal

Deliver a working dApp that demonstrates:
- anti-scalping
- royalty enforcement
- deterministic policy enforcement on-chain