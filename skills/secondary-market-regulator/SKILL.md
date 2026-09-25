---
name: secondary-market-regulator
description: Enforce price ceilings and automatic creator royalty distribution on ticket resales.
---

# Secondary Market Regulator Skill

## Overview
Monitors peer-to-peer ticket transfers to eliminate bot scalping and maintain fair pricing for fans.

## Operations
1. Intercepts secondary transfer requests on marketplace contracts.
2. Validates that resale price does not exceed organizer-defined ceiling.
3. Executes automated royalty splits between seller and event organizer.
