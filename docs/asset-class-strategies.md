# Asset-class strategy notes (v0.49)

These rules are research heuristics. Each class has an edge hypothesis, entry, invalidation, horizon, and size cap. They are not a promise of return. Version 0.49 adds adaptive periods, funding/on-chain proxies, volatility clustering, and enhanced multi-factor confirmation.

Regime labels:
- **trend**: multi-horizon move of at least 2.5% with controlled range
- **range**: neither stress nor trend
- **stress**: elevated average bar range or volatility clustering; directional ideas stand aside

## Major (BTC, ETH)

Hypothesis: liquid majors trend with multi-factor confirmation. Adaptive EMA (period scaled by ATR), Supertrend, Ichimoku cloud, Bollinger width, VWAP, MACD histogram, funding-rate correlation proxy, on-chain volume-flow and active-address proxies, and cross-asset correlation filter. Mean reversion only in range with BB squeeze and divergence. Cap 8%. Horizon 8-20 bars. Cost 8 bps.

## Large-cap alt

Hypothesis: breakouts need volume profile and relative strength. Entry: close above prior high with volume ≥1.3x avg, VWAP confirmation, MACD, multi-TF consistency, relative strength vs major, and non-elevated correlation. Cap 4%. Cost 14 bps.

## Stablecoin

Hypothesis: peg integrity. Adaptive deviation watch at 15 bps, depeg alert at 50 bps with volume confirmation. Risk gate forces size to zero.

## DeFi

Hypothesis: trend only in calm regimes. Stand aside if volatility clustering high, anomaly elevated, or ADX weak. Prefer Supertrend + on-chain activity proxy. Cap 2%. Cost 22 bps.

## Meme

Hypothesis: most bursts untradeable. Qualified long after ≥15% burst, rising volume-flow, StochRSI, consistency, and extension <40%. Horizon 3 bars. Cap 0.5%. Cost 45 bps.

## L2

Hypothesis: relative strength vs benchmark. Requires non-stress benchmark, MACD confirmation, adaptive MTF, and correlation filter. Cap 3%. Cost 16 bps.

## RWA

Hypothesis: slow trends. Halt on ≥8% gap or stress/anomaly. Volume filter preferred. Cap 2%, horizon 24 bars. Cost 12 bps.

## Perpetual

Hypothesis: negative funding with contained drift is carry. Funding ≥10 bps or flip is alert. Drift outside 4% blocks. Low anomaly required. Cap 2%. Cost 10 bps. Does not model liquidation or exchange risk.

## Still out of scope

- Live order routing, withdrawal, and trade API keys.
- Broker adapter (separate human-approved system).
- Claims about future returns.
