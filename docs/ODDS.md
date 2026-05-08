# Odds & House Edge

Full transparency on the math.

## x402 Roll

| Parameter | Value |
|-----------|-------|
| Cost per roll | 0.005 SOL |
| Win condition | Pick = rolled number (1–402) |
| Win probability | 1/402 = 0.2488% |
| Payout on win | 0.005 × 380 = 1.9 SOL |
| Expected payout | 1.9 × (1/402) = 0.004726 SOL |
| House edge | (0.005 − 0.004726) / 0.005 = **5.47%** |

## What this means

For every 402 rolls on average:
- 401 players lose 0.005 SOL each = 2.005 SOL collected
- 1 player wins 1.9 SOL
- House retains: 2.005 − 1.9 = **0.105 SOL**

## Expected value per roll

```
EV = (1/402 × 1.9 SOL) + (401/402 × −0.005 SOL)
EV = 0.004726 − 0.004975
EV = −0.000249 SOL per roll
```

You lose ~0.0002 SOL on average per roll, or about 5% of your stake.

## Note

These are theoretical odds based on fair randomness. See `SECURITY.md` for notes on the current randomness implementation.
