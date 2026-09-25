# Segregation of Duties (SOD): EventChain Agent

To guarantee Web3 protocol integrity, fraud prevention, and ticket authenticity, roles are segmented across four functions.

## Role Allocations

```
[Minting Registrar]        --> Role: Metadata Pinning & Contract Mint Engine (Maker)
        │
[Gate Entry Verifier]      --> Role: Dynamic QR Authenticator & Turnstile Guard (Executor)
        │
[Secondary Market Governor]--> Role: Resale Price Cap & Royalty Auditor (Checker)
        │
[Smart Contract Auditor]   --> Role: Blockchain Security & Reentrancy Guard (Auditor)
```

### 1. Minting Registrar (`maker`)
- Uploads ticket metadata to IPFS, validates organizer parameters, and executes ERC-721 batch minting transactions on Polygon.

### 2. Gate Entry Verifier (`executor`)
- Decodes time-decaying dynamic QR tokens, queries on-chain redemption status, and triggers turnstile admission gates.

### 3. Secondary Market Governor (`checker`)
- Monitors secondary transfer requests, enforces maximum resale price caps, and routes creator royalties.

### 4. Smart Contract Auditor (`auditor`)
- Audits smart contract bytecode, validates OpenZeppelin standards, monitors gas limits, and verifies non-custodial safety.
