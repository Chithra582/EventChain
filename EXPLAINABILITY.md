# EXPLAINABILITY — EventChain Agent

> **Admissibility & Transparency Report for OpenGAP / Agent Passport**  
> *Agent Name:* EventChain Agent (`eventchain-agent`)  
> *Specification:* OpenGAP v0.1.0  
> *Domain:* Finance / Decentralized Asset Management & Smart Contract Systems  

---

## 1. Overview & Architectural Purpose

EventChain Agent is an autonomous Web3 protocol intelligence and venue entry coordinator for decentralized event ticketing. Built upon Solidity smart contracts deployed on the Polygon PoS network, IPFS decentralized metadata storage (Pinata), and a Flutter cross-platform mobile client, the system replaces vulnerable centralized paper/barcode tickets with verifiable ERC-721 Non-Fungible Tokens.

The agent's primary purpose is to protect event organizers and attendees from ticket fraud, bot scalping, and invalid admissions. By monitoring smart contract transactions, validating cryptographically signed entry tokens, and enforcing programmable resale price caps, the agent ensures mathematical honesty throughout the entire ticketing lifecycle.

---

## 2. How the Agent Decides (Decision-Making Logic)

EventChain Agent operates across a deterministic four-stage blockchain verification pipeline:

```
[Event Creation & Ticket Mint] ──> [IPFS Metadata & Smart Contract] ──> [On-Chain Ownership Registry]
                                                                                       │
                                                                                       ▼
[Gate Admission & Burn/Redeem] <── [Anti-Double-Spend Validation] <── [Dynamic QR Scan Verification]
```

### 2.1 Ticket Minting & ERC-721 Smart Contract Routing
- **Decision:** Authenticates event organizer credentials and mints unique ERC-721 NFT tickets on Polygon.
- **Rules:**
  - Pins ticket metadata (event name, seat tier, date, artwork) to IPFS to obtain immutable CID hashes.
  - Deploys mint transactions with gas-optimized batch routines on Polygon PoS.
  - Binds each minted `tokenId` to the recipient's public Ethereum address (`ownerOf`).

### 2.2 Dynamic QR Entry Verification & Anti-Double-Spend Gate
- **Decision:** Validates scanned entry tickets at venue turnstiles and prevents duplicate admissions.
- **Rules:**
  - Generates time-sensitive (15-second decay), private-key-signed QR tokens to prevent screenshot sharing.
  - Queries `ownerOf(tokenId)` on the Polygon blockchain to confirm active ownership by the presenting wallet.
  - Checks the on-chain ticket status: if `isRedeemed == false`, transitions status to `Redeemed` and approves entry; if `true`, triggers an immediate turnstile rejection.

### 2.3 Secondary Market Price Capping & Resale Regulation
- **Decision:** Governs peer-to-peer ticket transfers to eliminate predatory scalping.
- **Rules:**
  - Enforces hardcoded resale price ceilings (e.g., maximum 110% of original face value).
  - Automatically routes programmable creator royalties (e.g., 5%) back to event organizers on secondary sales.

### 2.4 Organizer Settlement & Escrow Release
- **Decision:** Manages escrowed ticket revenue disbursements to event creators.
- **Rules:**
  - Locks ticket revenue in smart contract escrow until event verification milestones are met.
  - Automatically calculates and executes full attendee refunds in the event of cancellation.

---

## 3. Data Sources & Inputs Used

| Data Input | Source | Purpose | Data Handling & Privacy |
|---|---|---|---|
| **Smart Contract State** | Polygon PoS Blockchain RPC | Queries token ownership, redemption flags, and contract bytecode | Public immutable ledger data; zero private key exposure |
| **IPFS Metadata CIDs** | Decentralized IPFS gateway (Pinata) | Event schedules, venue seat allocations, and artwork URIs | Content-addressed public decentralized storage |
| **Dynamic QR Signatures** | Flutter mobile wallet app | Cryptographic proof of ticket possession at venue turnstiles | Ephemeral ECDSA signatures; verified in memory and discarded |
| **Organizer Parameters** | Event creator dashboard (Firebase) | Venue capacity, pricing tiers, and resale policy rules | Synchronized with on-chain smart contract configuration |

EventChain Agent complies with decentralized security and privacy standards:
- **No Private Key Access:** The agent never requests, stores, or handles private keys or seed phrases; all transactions are signed client-side via Web3 wallets.
- **GDPR Alignment:** Personally identifiable information (real names, physical home addresses) is kept off-chain in private encrypted datastores.
- **Zero Centralized Single Point of Failure:** Ticket validity is determined by decentralized consensus on the Polygon blockchain.

---

## 4. Known Limitations & Failure Modes

Reviewers, organizers, and attendees should note the following system boundaries:

1. **Blockchain Gas Spikes & RPC Latency:**
   - *Limitation:* Extreme network congestion on Polygon PoS can occasionally delay minting transactions or balance queries.
   - *Mitigation:* The mobile client employs local cryptographic signature caching and resilient multi-RPC fallback providers to ensure turnstile throughput.

2. **Offline Venue Gate Scanners:**
   - *Limitation:* If venue internet infrastructure drops completely, real-time RPC calls to Polygon cannot verify new on-chain transfers made seconds earlier.
   - *Mitigation:* Gate turnstiles maintain an encrypted local snapshot of all issued ticket public keys synchronized 1 hour prior to doors opening, allowing secure offline asymmetric validation.

3. **Irreversible On-Chain Transactions:**
   - *Limitation:* Blockchain transactions cannot be reversed once confirmed by consensus; transfers to incorrect recipient wallet addresses cannot be undone by the agent.
   - *Mitigation:* The mobile interface incorporates QR-based address scanning, checksum validation, and confirmation prompts before executing on-chain transfers.

4. **Non-Custodial Account Recovery:**
   - *Limitation:* If an attendee permanently loses access to their private key or recovery phrase, the agent cannot regenerate or restore wallet ownership.
   - *Mitigation:* The onboarding flow guides users through secure seed phrase backup and supports social recovery and smart-contract wallet abstractions.

---

## 5. Verification, Safety & Human Oversight

- **Organizer Gate Override:** Turnstile supervisors hold manual administrative override authority to admit attendees in contested hardware failure scenarios.
- **Smart Contract Circuit Breakers (Pausable):** Deployed contracts include OpenZeppelin `Pausable` guards, allowing organizers to halt transfers in the event of a detected exploit.
- **Immutable On-Chain Audit Trail:** Every mint, transfer, resale price, and redemption event is permanently recorded on Polygon for complete post-event auditing.
- **Kill Switch:** Assistant services and indexing daemons can be paused instantly with zero impact on underlying decentralized smart contracts.
