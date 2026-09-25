---
name: entry-qr-authenticator
description: Verify dynamic time-decaying QR codes and validate ticket redemption status at venue gates.
---

# Entry QR Authenticator Skill

## Overview
Authenticates attendee entry credentials at venue turnstiles by verifying cryptographic signatures against Polygon state.

## Operations
1. Scans and decodes dynamic QR signature payload.
2. Confirms active token ownership on-chain via `ownerOf(tokenId)`.
3. Verifies `isRedeemed == false`, updates status to `Redeemed`, and signals turnstile admission.
