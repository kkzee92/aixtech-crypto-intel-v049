# AIxTech crypto intel v0.49: paper-only trading information system

Research harness for automated cryptocurrency **information** and paper strategy evaluation. Does not place live orders, does not store exchange secrets, and is not financial advice.

Builds on [zeekiankok92/aixtech-agent-harness-demo](https://github.com/zeekiankok92/aixtech-agent-harness-demo) secure AI-agent practices and prior kkzee92 versions.

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![version](https://img.shields.io/badge/version-0.49.0-blue)
![mode](https://img.shields.io/badge/execution-paper%20only-orange)
![Licence](https://img.shields.io/badge/licence-MIT-green)

## Enhancements in v0.49

- Advanced multi-factor strategies per asset class: adaptive EMA/ATR periods, funding-rate correlation proxies, on-chain volume-flow and active-address proxies, volatility clustering (GARCH-style), multi-horizon consistency, RSI/MACD/Stochastic divergence, Supertrend + Ichimoku + Bollinger + VWAP + ADX confirmation stack.
- Portfolio-level correlation risk gate with adaptive sizing under high vol/anomaly/correlation regimes.
- Strengthened zero-trust cyber/data security: expanded redaction (BIP39, WIF, PEM, AWS, GitHub PATs, high-entropy, Solana, session tokens, hardware wallet exports), sealed multi-hash lineage (SHA-256 + BLAKE3-style), isolation anomaly detection, entropy scoring, residency stamps, consecutive-action counters, source attestation.
- Eight asset classes with refined playbooks, risk caps, and class-specific cost models.
- Research only; synthetic fixtures recommended. AI-agent harness friendly.

See [docs/asset-class-strategies.md](docs/asset-class-strategies.md) and [docs/security-architecture.md](docs/security-architecture.md).

## What it does

- Classifies into eight asset classes with enhanced multi-factor research rules.
- Labels regime (trend/range/stress) + volatility tier + anomaly score + correlation regime.
- Scores signal then multi-gate risk (class caps, confidence, correlation, anomaly, drawdown).
- Paper fills with class costs; hash-chained audit with lineage seals.
- No live execution, no secret storage.

| Asset class | Enhanced research rule | Risk cap | Cost |
|---|---|---|---|
| Major | Adaptive multi-factor EMA + Supertrend + Ichimoku + BB + VWAP + MACD + funding/on-chain proxies + correlation-adjusted outside stress | 8% | 8 bps |
| Large-cap alt | Volume-profile breakout + VWAP + MACD + multi-TF + relative strength vs major + correlation filter | 4% | 14 bps |
| Stablecoin | Adaptive peg deviation (15-50 bps) with volume confirmation | 0% | n/a |
| DeFi | Calm multi-scale + low anomaly + Supertrend + ADX + on-chain activity proxy | 2% | 22 bps |
| Meme | Qualified burst + StochRSI + consistency + hard horizon + volume-flow decay | 0.5% | 45 bps |
| L2 | Relative strength + MACD vs benchmark + adaptive MTF + correlation confirmation | 3% | 16 bps |
| RWA | Slow multi-scale + gap/anomaly halt + volume filter | 2% | 12 bps |
| Perpetual | Negative funding carry + contained drift + low anomaly + funding flip alert | 2% | 10 bps |

## Run

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
PYTHONPATH=src python -m crypto_intel.demo
PYTHONPATH=src pytest tests/ -q
```

## Controls

Paper-only mode guard. No trade keys. Class caps, confidence floors, kill switch, drawdown, correlation, anomaly gates. Hash-chained audit + sealed multi-hash lineage. Expanded redaction. PDPA-style tripwire. gitleaks recommended in CI.

## Honesty

No live connector included. Strategy scores describe synthetic data. Not financial, legal, or compliance advice. Research only.
