## Table of Contents

**[Market Microstructure Research](#market-microstructure-research)**

- [Market Maker Simulator](#market-maker-simulator)

**[Execution Infrastructure](#execution-infrastructure)**

- [Low-Liquidity Execution Engine](#low-liquidity-execution-engine)

**[Legacy / Earlier Work](#legacy--earlier-work)**

- **[Algorithmic Trading](#algorithmic-trading)**
  - [Uhl MA Crossover Strategy (PineScript, NodeJS)](#uhl-ma-crossover-strategy-pinescript-nodejs)
- **[Studies](#studies)**
  - [Mean Reversion Compression/Expansion study](#mean-reversion-compressionexpansion-study)
  - ["MACD-zero compression" study](#macd-zero-compression-study)
  - [Volume & Trend Scanner](#volume--trend-scanner)
- **[Other Tools (Crypto)](#other-tools-crypto)**
  - [Neutron blockchain token bulk-sender](#neutron-blockchain-token-bulk-sender)
  - [Bitfinex Auto-Stop with 1:1 Scale-out](#bitfinex-auto-stop-with-11-scale-out)

**[Let's connect](#lets-connect)**

# Market Microstructure Research

## [Market Maker Simulator](https://github.com/cryptomius/mm-parameter-lab)

A discrete-time ***\*Avellaneda–Stoikov\**** market-making simulator with a stress-scenario library, operating regime controller, toggleable risk interventions, and a real-time UI for poking the quoter mid-flight.

Built to study how the Avellaneda-Stoikov algorithm responds to different market regimes — including crypto-specific stresses like vesting oversupply — and how various risk interventions perform under each. Includes a headless backtesting engine for reproducible analysis.

![Market Maker Simulator](https://github.com/cryptomius/mm-parameter-lab/raw/main/docs/snapshot.png)

Link: [Market Maker Simulator & Parameter Lab on Github.com](https://github.com/cryptomius/mm-parameter-lab)

# Execution Infrastructure

## Low-Liquidity Execution Engine 

An order placement system designed to minimise market impact and detection in thin order books. 

Implements randomised order sizing and timing to avoid signature-based detection by other algorithms, with opportunistic order-book-aware execution when transient liquidity appears at favourable prices. CCXT-based, exchange-agnostic.

Used in production to manage systematic liquidations across 200+ low-liquidity tokens with no observable market impact.

![Lowcap Ease Parameters](assets/lowcapease-params.png)
![Lowcap Ease](assets/lowcapease.png)

Link: Proprietary 

# Legacy / Earlier Work

Earlier work from when I first started trading (2016-2018). Included for completeness — they reflect the retail-discretionary frameworks I was learning at the time.

## Algorithmic Trading 

### Uhl MA Crossover Strategy (PineScript, NodeJS)

Strategy implementation of [Alex Glover's](https://www.tradingview.com/script/Hl1Sw0I4-Uhl-MA-Crossover-System/) adaptation of Andreas Uhl moving average formula (professor at Salzburg University). Essentially the algorithm attempts to minimise the frequency of slow vs fast moving average cross-overs during sideways market conditions. 

I converted the indicator into a strategy for backtesting and tested additional signal invalidation layers, loss mitigation, risk management & profit target methodologies.

I ran this strategy live on 4H and 8H candles across several high-liquidity crypto assets (spot for long, quarterly futures or perp futures for short) using segregated CEX sub-accounts. I wrote the infrastructure to calculate the strategy data from CEX API data and perform the trades directly (NodeJS with CCXT).

Monte Carlo simulations were positive, but real-world outcomes showed net sideways profitability so I put the live execution on ice.

![UHL MA Crossover Strategy](assets/uhl-strategy.png)

Link: Proprietary system (not public)

## Studies

### [Mean Reversion Compression/Expansion study](https://www.tradingview.com/script/dIODLr62-Crypto-Cradle-v6/)

A study of mean-reverting compression-then-expansion regimes in crypto, with statistical significance testing on historical data.

![Cradle TradingView](https://s3.tradingview.com/c/cNHOAIDP_mid.png)


### ["MACD-zero compression" study](https://www.tradingview.com/script/rwBArbXJ-Explosive-Potential/)

This study isolates when MACD is within a specified range (close to 0) and price action is constrained.

![Explosive Potential](https://s3.tradingview.com/r/rwBArbXJ_mid.png)

### Volume & Trend Scanner

Prototype built to quickly scan for early volume signals preceding large price movement. The system ingests daily price and volume data from Coingecko API, applies trend, BTC correlation & volume threshold algorithms, and stores locally for fast display of trading shortlist.

Volume threshold detector is a derivative of ATR with multiplier and trend is zig-zag algorithm based (HH, HL).

Other features include exchange-based liquidity snapshots, daily trending coin data, social media sentiment.

![Crypto Market Volume Scanner](assets/volume-scanner.jpg)

Link: Proprietary system (not public)

## Other Tools (Crypto)

## [Neutron blockchain token bulk-sender](https://github.com/cryptomius/neutron-bulk-sender)
Written to perform bulk USDC transfers to Neutron blockchain recipients list (CSV).

Requires a Neutron blockchain wallet, RPC address, source wallet mnemonic phrase, and CSV containing destination address & amount pairs. 

The CSV will be updated with the transaction hash of the sent amount, which also avoids duplicate sending if the script gets interrupted.

---

## [Bitfinex Auto-Stop with 1:1 Scale-out](https://github.com/cryptomius/Bitfinex-Auto-Stop-121-Scale-Out)

Retail trading tool that waits for a specified entry price, opens a position of a nominated amount, then automatically places a 100% stop order and 50% scale-out limit order at 1:1 R:R. Built to address a gap in trading instrumentation offered by Bitfinex.

Link: [Bitfinex Auto-Stop with 1:1 Scale-out](https://github.com/cryptomius/Bitfinex-Auto-Stop-121-Scale-Out)

---

# **Let's connect**

**LinkedIn**: https://www.linkedin.com/in/smurdoch/
