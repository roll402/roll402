# Odds & House Edge

Full transparency on the math.

## x402 Roll

| Parameter | Value |
|-----------|-------|
| Cost per roll | 0.005 SOL |
| Win condition | Pick = rolled number (1–402) |
| Win probability | 1/402 ≈ 0.2488% |
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

You lose ~0.00025 SOL on average per roll, or about 5% of your stake.

## Variance examples

The 5.47% edge is the long-term average. Short sessions are dominated by variance — most rolls lose, and one hit pays for hundreds.

| Rolls | Expected wins | Probability of at least one win |
|-------|---------------|---------------------------------|
| 50    | 0.124         | 11.7% |
| 100   | 0.249         | 22.0% |
| 200   | 0.498         | 39.3% |
| 400   | 0.995         | 63.0% |
| 1000  | 2.488         | 91.7% |
| 2000  | 4.975         | 99.3% |

**Translation:** even after 400 rolls (~2 SOL spent), roughly one in three players still hasn't hit. The geometry is brutal. That's the trade-off for a ×380 payout.

## Comparison

| Game | House edge |
|------|-----------|
| Roll402 | ~5.5% |
| Roulette (European) | 2.7% |
| Roulette (American) | 5.26% |
| Slots (typical) | 5–15% |

## Note

These are theoretical odds based on fair randomness. See [`SECURITY.md`](../SECURITY.md) for notes on the current randomness implementation.
