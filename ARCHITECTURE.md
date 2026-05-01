# ROLL402 — Architecture

## Overview

Roll402 is a single-page Next.js application. There is no backend — all logic runs client-side or directly on Solana.

## Payment flow

```
User picks number (1-402)
        ↓
User clicks "ROLL 402"
        ↓
Frontend builds SOL transfer transaction
  from: user wallet
  to:   PAYMENT_ADDRESS (house wallet)
  amount: 0.005 SOL
        ↓
User signs via wallet adapter (Phantom / Solflare / MetaMask Snap)
        ↓
Transaction submitted to Solana mainnet
        ↓
Frontend polls for confirmation
        ↓
On confirmation: extract transaction signature hash
        ↓
Derive result: hash → integer mod 402 + 1
  if result === user's number → WIN
  else → LOSE
        ↓
WIN: house wallet sends payout (0.005 × 380 = 1.9 SOL)
LOSE: nothing sent back
```

## Randomness

The outcome is derived from the confirmed transaction signature:

```typescript
function deriveResult(txSignature: string, max: number): number {
  // Take first 8 bytes of signature hash
  const hash = sha256(txSignature).slice(0, 8);
  const num = parseInt(hash, 16);
  return (num % max) + 1;
}
```

This is deterministic — given the same signature, the result is always the same. The signature is not known until the transaction is confirmed on-chain, making it impossible to predict before payment.

**Limitation**: This is client-side. A malicious frontend could theoretically show a different result than what the hash dictates. Provably fair upgrade: Switchboard VRF (see `SECURITY.md`).
