---
name: nft-ticket-issuer
description: Mint unique ERC-721 NFT tickets on Polygon with decentralized IPFS metadata pinning.
---

# NFT Ticket Issuer Skill

## Overview
Deploys and manages ERC-721 NFT ticket generation on Polygon PoS, pinning event attributes to IPFS via Pinata.

## Operations
1. Validates event metadata schema (name, date, seat, tier).
2. Uploads metadata to IPFS and captures deterministic CID.
3. Executes gas-optimized contract mint transaction to recipient address.
