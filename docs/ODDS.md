# Odds & House Edge

Full transparency on the math.

## x402 Roll

| Parameter | Value |
|-----------|-------|
| Cost per roll | 0.005 SOL |
| Win condition | Pick = rolled number (1–402) |
| Win probability | 1/402 = 0.2488% |
| Payout on win | 0.005 × 380 = 1.9 SOL |
| Expected payout | 1.9 × (1/402) = 0.00472 SOL |
| House edge | (0.005 - 0.00472) / 0.005 = **5.6%** |

## What this means

For every 402 rolls on average:
- 401 players lose 0.005 SOL each = 2.005 SOL collected
- 1 player wins 1.9 SOL
- House retains: 2.005 - 1.9 = **0.105 SOL**

## Expected value per roll

```
EV = (1/402 × 1.9 SOL) + (401/402 × -0.005 SOL)
EV = 0.00472 - 0.00499
EV ≈ -0.00027 SOL per roll
```

## Note

These are theoretical odds based on fair randomness. See `SECURITY.md` for notes on the current randomness implementation.
