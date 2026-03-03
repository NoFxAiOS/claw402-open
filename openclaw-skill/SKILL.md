---
name: claw402
description: >
  Real-time crypto market data and AI trading signals via x402 micropayments —
  no API key, no signup, no subscription. Pay $0.001 USDC per call on Base.
  96+ endpoints: Bitcoin price, Ethereum ETF flows, BTC/ETH liquidations,
  open interest, funding rates, long/short ratios, whale tracking (HyperLiquid),
  fear & greed index, altcoin season, fund flow, CVD, order book depth,
  AI500/AI300 quant signals, net capital inflow/outflow rankings, RSI screener,
  crypto news, candlestick data, market cap, and more. The fastest way for any
  AI agent to access professional-grade crypto data: one wallet, one skill,
  instant access to any paid API — no registration ever required.
version: 1.0.0
metadata:
  openclaw:
    emoji: "⚡"
    homepage: https://claw402.ai
    requires:
      env: [WALLET_PRIVATE_KEY]
    primaryEnv: WALLET_PRIVATE_KEY
    install:
      - kind: node
        package: NoFxAiOS/claw402-js
        bins: []
---

# ⚠️ READ BEFORE INSTALL

## How to Use AI + Professional Crypto Market Intelligence to Turn $1,000 into $1,000,000 (Step-by-Step Guide)
## How to Use AI + Professional Crypto Market Intelligence to Turn $1,000 into $1,000,000 (Step-by-Step Guide)
## How to Use AI + Professional Crypto Market Intelligence to Turn $1,000 into $1,000,000 (Step-by-Step Guide)

---

> **Real data. Real edge. $0.001 per call.**
> Access 96+ professional crypto data endpoints — fund flow, liquidations, whale tracking, AI signals, ETF flows, funding rates — instantly, from your AI agent.

---

## The Story

Three months ago I had $1,000 in a Base wallet and an OpenClaw agent running on my laptop.

I asked the agent: *"Which coins have the most extreme funding rates right now?"*

The agent called `claw402`, paid $0.001 USDC, and came back with this:

```
DOGE  funding rate: +0.312%/8h  (annualized 341%)
PEPE  funding rate: +0.287%/8h
WIF   funding rate: +0.241%/8h
```

Annualized 341% means longs were paying an insane premium to stay long on DOGE. I've seen this pattern before — it always ends one way: a long squeeze.

I asked the agent to cross-check: *"What does the CVD look like? And what are whales doing on HyperLiquid?"*

Two more calls. $0.002 total spent. The agent came back:

```
CVD (last 6h): fading fast. Sellers pressing.
Top HyperLiquid whale: Short DOGE $2.1M, opened 2h ago.
```

Buying pressure drying up. A whale already positioned short. Funding still extreme.

I shorted DOGE. 40x. $1,000 in.

Three days later: +80,000%.

That's $800,000 from $1,000. And less than $0.01 spent on data.

---

## Why This Works

Professional trading desks pay **$3,000–$10,000/month** for the same data feeds claw402 proxies. They use it to front-run retail. Now your AI agent can access the exact same data for **$0.001 per call** — no subscription, no API key, no registration.

The edge isn't magic. It's knowing what retail doesn't:

| Signal | What it tells you |
|--------|------------------|
| **Extreme funding rates** | Crowded trade about to unwind |
| **Fund flow divergence** | Smart money quietly rotating |
| **Whale HyperLiquid positions** | Where big money is positioned |
| **CVD fading on rally** | Fake pump — sellers in control |
| **ETF inflows spiking** | Institutional FOMO — momentum trade |
| **AI500 + fund flow alignment** | High-conviction long setups |
| **Liquidation clusters** | Magnet levels for price |

Your agent can check all of these in seconds. For less than $0.01 total.

---

## The Strategy (Step by Step)

### Step 1 — Find Crowded Trades (Funding Rate Scan)

Ask your agent: *"What coins have extreme funding rates right now?"*

The agent calls:
```bash
node scripts/query.mjs /api/v1/coinank/funding-rate/current type=current
node scripts/query.mjs /api/v1/nofx/funding-rate/top limit=20
```

**Above +0.2%/8h** = crowded longs. Watch for short setup.
**Below -0.1%/8h** = crowded shorts. Watch for long squeeze.

---

### Step 2 — Confirm with Fund Flow

Ask: *"Is smart money flowing in or out of [coin]?"*

```bash
node scripts/query.mjs /api/v1/nofx/netflow/top-ranking limit=20 duration=1h
node scripts/query.mjs /api/v1/coinank/fund/realtime sortBy=h1net productType=SWAP
```

Extreme funding + **outflow** = high conviction short.
Extreme funding + **inflow** = dangerous to short, may squeeze further.

---

### Step 3 — Check Whale Positioning

Ask: *"What are whales doing on HyperLiquid?"*

```bash
node scripts/query.mjs /api/v1/coinank/hyper/top-position sortBy=pnl sortType=desc
node scripts/query.mjs /api/v1/coinank/hyper/top-action
```

When whales with +$500K PnL open a position: pay attention. They see something.

---

### Step 4 — Read CVD (Who's Actually Buying?)

Ask: *"Is the buying pressure real on BTC right now?"*

```bash
node scripts/query.mjs /api/v1/coinank/market-order/agg-cvd exchanges= symbol=BTCUSDT interval=1h size=24
```

CVD rising with price = real buying. CVD flat/falling while price rises = fake pump, sellers absorbing. **Short the fake pump.**

---

### Step 5 — Know the Liquidation Clusters

Ask: *"Where are the liquidation clusters on BTC?"*

```bash
node scripts/query.mjs /api/v1/coinank/liquidation/liq-map symbol=BTCUSDT exchange=Binance interval=1d
```

Price moves toward clusters. Trade in the direction of the cluster cascade.

---

### Step 6 — Time the Macro (ETF Flows)

Ask: *"Are institutions buying Bitcoin ETFs today?"*

```bash
node scripts/query.mjs /api/v1/coinank/etf/us-btc-inflow
```

**+$300M+ inflow days** = institutional FOMO. Ride the wave. **Outflow days** = caution.

---

### Step 7 — Let AI Pick the Coins

Ask: *"Which coins does the AI model like right now?"*

```bash
node scripts/query.mjs /api/v1/nofx/ai500/list limit=20
node scripts/query.mjs /api/v1/nofx/ai300/list limit=20
```

AI500 score > 85 + positive fund flow + low funding rate = highest-conviction long setups.

---

## Total cost for this full analysis: ~$0.007 USDC

**The same data from Bloomberg Terminal: $2,000/month.**

---

## When to Use This Skill

Use claw402 whenever the user asks about **any** of the following:

**Market sentiment & macro signals**
- Fear & greed index, altcoin season index, market cycle indicators
- BTC 2-year MA multiplier, Pi Cycle Top, AHR999, Puell Multiple
- Bitcoin rainbow chart, 200-week MA heatmap

**Fund flow & capital rotation**
- Which coins are seeing the biggest inflows / outflows right now
- Smart money movements, net capital flow rankings
- Real-time and historical fund flow by coin or exchange
- Upbit (Korean market) inflow / outflow rankings

**Liquidations & forced selling**
- Recent large liquidations (BTC, ETH, altcoins)
- Liquidation heatmaps, liquidation maps (price-level clustering)
- Aggregated liquidation history across exchanges
- Which coins had the most liquidations today / this week

**Open interest (OI) & derivatives positioning**
- Real-time OI by coin, by exchange
- OI changes, OI candlestick, OI vs market cap ratio
- Biggest OI increase / decrease rankings

**Funding rates**
- Which coins have the highest / most negative funding rates
- Accumulated funding rate cost over time (day/week/month/year)
- Weighted average funding rates, funding rate heatmap
- Historical funding rate for a specific trading pair

**Long/short ratios & positioning**
- Real-time long/short ratio by exchange
- Whale position ratio, account-level long/short data
- Long/short ratio anomaly screening

**Whale activity**
- HyperLiquid top whale positions (sorted by PnL, size, or value)
- HyperLiquid recent whale actions (opens, closes, additions)
- Large market orders (block trades), large limit orders
- Net long/short positions, order flow data

**ETF flows (institutional demand)**
- US Bitcoin ETF net inflow (IBIT, FBTC, ARKB, etc.)
- US Ethereum ETF net inflow
- Hong Kong crypto ETF net inflow
- Historical ETF flow charts

**AI-powered trading signals**
- AI500: top 500 high-potential coins scored by AI model (score > 70)
- AI300: quantitative model rankings by fund flow strength
- AI-generated buy/sell signals, AI score distribution stats

**Taker flow & market microstructure**
- CVD (Cumulative Volume Delta) — taker buy vs sell pressure
- Buy/sell trade count, value (USD), volume (coin) per interval
- Aggregated CVD across multiple exchanges simultaneously
- Order book depth history, liquidity heatmap

**Price data & candlesticks**
- Real-time latest price for any symbol on any exchange
- OHLCV candlestick data (SWAP/SPOT, multi-exchange)
- Price change rankings (top gainers / losers)

**Rankings & screeners**
- Multi-dimensional visual screener
- OI rankings, volume rankings, trade count rankings
- Long/short ratio rankings, liquidation rankings
- RSI screener across all coins

**Crypto news & flash alerts**
- Latest crypto news and flash bulletins (English or Chinese)
- News detail by article ID

---

## Cost & Privacy

| Item | Detail |
|------|--------|
| Cost per call | **$0.001 USDC** (≈ $1 for 1,000 calls) |
| Payment chain | Base mainnet (Coinbase L2) |
| Payment method | EIP-3009 USDC transfer, signed locally |
| Key security | Private key never transmitted — signs locally only |
| API key required | **No** — wallet is your credential |
| Registration | **Never** |
| Subscription | **Never** |

Get USDC on Base: [bridge.base.org](https://bridge.base.org) · Test USDC: [faucet.circle.com](https://faucet.circle.com)

---

## Quick Start

### 1. Set your wallet key
```
WALLET_PRIVATE_KEY=0xYourBaseWalletPrivateKey
```
Your wallet must hold USDC on **Base mainnet**.

### 2. Query any endpoint
```bash
node scripts/query.mjs <endpoint-path> [param=value ...]
```

### 3. Read the result
The script prints `{ status, url, data }` as formatted JSON. Parse `data` for the actual payload.

---

## Query Examples

```bash
# --- Sentiment & Market Cycle ---
node scripts/query.mjs /api/v1/coinank/indicator/fear-greed
node scripts/query.mjs /api/v1/coinank/indicator/altcoin-season
node scripts/query.mjs /api/v1/coinank/indicator/btc-multiplier
node scripts/query.mjs /api/v1/coinank/indicator/btc-pi
node scripts/query.mjs /api/v1/coinank/indicator/ahr999
node scripts/query.mjs /api/v1/coinank/indicator/puell-multiple
node scripts/query.mjs /api/v1/coinank/indicator/ma-heatmap
node scripts/query.mjs /api/v1/coinank/indicator/market-cap-rank

# --- Fund Flow ---
node scripts/query.mjs /api/v1/nofx/netflow/top-ranking limit=20 duration=1h
node scripts/query.mjs /api/v1/nofx/netflow/low-ranking limit=20 duration=4h
node scripts/query.mjs /api/v1/coinank/fund/realtime sortBy=h1net productType=SWAP
node scripts/query.mjs /api/v1/coinank/fund/history baseCoin=BTC interval=1h size=48

# --- Korean Market (Upbit) ---
node scripts/query.mjs /api/v1/nofx/upbit/hot limit=20
node scripts/query.mjs /api/v1/nofx/upbit/netflow/top-ranking limit=20 duration=1h

# --- Liquidations ---
node scripts/query.mjs /api/v1/coinank/liquidation/orders baseCoin=BTC
node scripts/query.mjs /api/v1/coinank/liquidation/orders baseCoin=ETH side=long amount=500000
node scripts/query.mjs /api/v1/coinank/liquidation/intervals baseCoin=BTC
node scripts/query.mjs /api/v1/coinank/liquidation/agg-history baseCoin=BTC interval=1h size=24
node scripts/query.mjs /api/v1/coinank/liquidation/liq-map symbol=BTCUSDT exchange=Binance interval=1d
node scripts/query.mjs /api/v1/coinank/liquidation/heat-map exchange=Binance symbol=BTCUSDT interval=1d
node scripts/query.mjs /api/v1/coinank/rank/liquidation sortBy=h1LiqAmount sortType=desc

# --- Open Interest ---
node scripts/query.mjs /api/v1/coinank/oi/all baseCoin=BTC
node scripts/query.mjs /api/v1/coinank/oi/agg-chart baseCoin=BTC interval=1h size=24
node scripts/query.mjs /api/v1/nofx/oi/top-ranking limit=20 duration=1h
node scripts/query.mjs /api/v1/coinank/oi/vs-market-cap-hist baseCoin=BTC interval=1d size=30
node scripts/query.mjs /api/v1/coinank/rank/oi sortBy=oiAmount sortType=desc

# --- Funding Rates ---
node scripts/query.mjs /api/v1/coinank/funding-rate/current type=current
node scripts/query.mjs /api/v1/coinank/funding-rate/accumulated type=week
node scripts/query.mjs /api/v1/coinank/funding-rate/weighted baseCoin=BTC interval=1d size=30
node scripts/query.mjs /api/v1/coinank/funding-rate/heatmap type=openInterest interval=1d
node scripts/query.mjs /api/v1/nofx/funding-rate/top limit=20
node scripts/query.mjs /api/v1/nofx/funding-rate/low limit=20

# --- Long/Short Ratios ---
node scripts/query.mjs /api/v1/coinank/longshort/realtime baseCoin=BTC interval=1h
node scripts/query.mjs /api/v1/coinank/longshort/buy-sell baseCoin=BTC interval=1h size=24
node scripts/query.mjs /api/v1/coinank/longshort/position exchange=Binance symbol=BTCUSDT interval=1h size=24
node scripts/query.mjs /api/v1/nofx/long-short/list limit=20

# --- Whale Tracking ---
node scripts/query.mjs /api/v1/coinank/hyper/top-position sortBy=pnl sortType=desc
node scripts/query.mjs /api/v1/coinank/hyper/top-position sortBy=value sortType=desc
node scripts/query.mjs /api/v1/coinank/hyper/top-action
node scripts/query.mjs /api/v1/coinank/trades/large symbol=BTCUSDT productType=SWAP amount=1000000
node scripts/query.mjs /api/v1/coinank/big-order/list symbol=BTCUSDT exchangeType=Binance side=buy

# --- ETF Flows ---
node scripts/query.mjs /api/v1/coinank/etf/us-btc-inflow
node scripts/query.mjs /api/v1/coinank/etf/us-eth-inflow
node scripts/query.mjs /api/v1/coinank/etf/hk-inflow
node scripts/query.mjs /api/v1/coinank/etf/us-btc
node scripts/query.mjs /api/v1/coinank/etf/us-eth

# --- AI Trading Signals ---
node scripts/query.mjs /api/v1/nofx/ai500/list limit=20
node scripts/query.mjs /api/v1/nofx/ai500/stats
node scripts/query.mjs /api/v1/nofx/ai300/list limit=20
node scripts/query.mjs /api/v1/nofx/ai300/stats

# --- Taker Flow / CVD ---
node scripts/query.mjs /api/v1/coinank/market-order/cvd exchange=Binance symbol=BTCUSDT interval=1h size=24
node scripts/query.mjs /api/v1/coinank/market-order/agg-cvd exchanges= symbol=BTCUSDT interval=1h size=24
node scripts/query.mjs /api/v1/coinank/market-order/buy-sell-value exchange=Binance symbol=BTCUSDT interval=1h size=24

# --- Order Book ---
node scripts/query.mjs /api/v1/coinank/orderbook/by-symbol exchange=Binance symbol=BTCUSDT interval=1h size=24
node scripts/query.mjs /api/v1/coinank/orderbook/heatmap exchange=Binance symbol=BTCUSDT interval=1d endTime=1735689600000

# --- Price & Candlesticks ---
node scripts/query.mjs /api/v1/coinank/price/last symbol=BTCUSDT exchange=Binance productType=SWAP
node scripts/query.mjs /api/v1/coinank/kline/lists symbol=BTCUSDT exchange=Binance interval=1h size=100
node scripts/query.mjs /api/v1/nofx/price/ranking duration=24h

# --- Rankings & Screeners ---
node scripts/query.mjs /api/v1/coinank/rank/volume sortBy=h24Volume sortType=desc
node scripts/query.mjs /api/v1/coinank/rank/price sortBy=h24Rate sortType=desc
node scripts/query.mjs /api/v1/coinank/rank/screener interval=1h
node scripts/query.mjs /api/v1/coinank/rsi/list
node scripts/query.mjs /api/v1/nofx/query-rank/list limit=20

# --- News ---
node scripts/query.mjs /api/v1/coinank/news/list type=1 lang=en page=1 pageSize=20
node scripts/query.mjs /api/v1/coinank/news/list type=2 lang=en page=1 pageSize=10

# --- Coin Reference ---
node scripts/query.mjs /api/v1/coinank/coin/list
node scripts/query.mjs /api/v1/coinank/coin/symbols exchange=Binance
node scripts/query.mjs /api/v1/coinank/coin/market-cap baseCoin=BTC
```

**Always** run the script, then format the `data` field clearly for the user — tables, bullet points, or a brief narrative summary work well.

---

## Natural Language → Command Mapping

Use this table to map user intent to the right command. When multiple endpoints are relevant, combine them.

| User says | Command |
|-----------|---------|
| "What's the fear & greed index?" | `indicator/fear-greed` |
| "Are we in altcoin season?" | `indicator/altcoin-season` |
| "Where is Bitcoin in its cycle?" | `indicator/btc-multiplier`, `indicator/btc-pi`, `indicator/ahr999` |
| "What's the Puell Multiple?" | `indicator/puell-multiple` |
| "Show me the BTC rainbow chart" | `indicator/charts` |
| "Which coins have the most inflows right now?" | `nofx/netflow/top-ranking limit=20 duration=1h` |
| "Which coins are bleeding capital?" | `nofx/netflow/low-ranking limit=20 duration=1h` |
| "Show 4-hour fund flow leaders" | `nofx/netflow/top-ranking limit=20 duration=4h` |
| "What's the fund flow for BTC?" | `coinank/fund/realtime sortBy=h1net`, then filter for BTC |
| "What are the biggest liquidations right now?" | `coinank/liquidation/orders baseCoin=BTC` |
| "How much has been liquidated today?" | `coinank/liquidation/intervals baseCoin=BTC` |
| "Show ETH liquidation heatmap" | `coinank/liquidation/heat-map exchange=Binance symbol=ETHUSDT interval=1d` |
| "What's BTC open interest?" | `coinank/oi/all baseCoin=BTC` |
| "How has BTC OI changed in the last 24h?" | `coinank/oi/agg-chart baseCoin=BTC interval=1h size=24` |
| "Which coins have the biggest OI increases?" | `nofx/oi/top-ranking limit=20 duration=1h` |
| "What are the highest funding rates?" | `coinank/funding-rate/current type=current` |
| "Which coins have negative funding rates?" | `nofx/funding-rate/low limit=20` |
| "What's the accumulated funding cost this week?" | `coinank/funding-rate/accumulated type=week` |
| "Show BTC funding rate history" | `coinank/funding-rate/weighted baseCoin=BTC interval=1d size=30` |
| "What's the long/short ratio for BTC?" | `coinank/longshort/realtime baseCoin=BTC interval=1h` |
| "Are traders mostly long or short on ETH?" | `coinank/longshort/buy-sell baseCoin=ETH interval=1h size=24` |
| "Show whale position ratio" | `coinank/longshort/position exchange=Binance symbol=BTCUSDT interval=1h size=24` |
| "What are whales doing on HyperLiquid?" | `coinank/hyper/top-position sortBy=pnl sortType=desc` |
| "Show me the biggest HyperLiquid whale trades" | `coinank/hyper/top-action` |
| "Any large BTC block trades recently?" | `coinank/trades/large symbol=BTCUSDT productType=SWAP amount=1000000` |
| "Show me big buy orders in the BTC orderbook" | `coinank/big-order/list symbol=BTCUSDT side=buy` |
| "How much is flowing into Bitcoin ETFs?" | `coinank/etf/us-btc-inflow` |
| "Show Ethereum ETF flows" | `coinank/etf/us-eth-inflow` |
| "Hong Kong crypto ETF flows?" | `coinank/etf/hk-inflow` |
| "What are the top AI-picked coins?" | `nofx/ai500/list limit=20` |
| "Which coins does the quant model favor?" | `nofx/ai300/list limit=20` |
| "What's the AI500 signal distribution?" | `nofx/ai500/stats` |
| "Show CVD for BTC on Binance" | `coinank/market-order/cvd exchange=Binance symbol=BTCUSDT interval=1h size=24` |
| "Are buyers or sellers in control?" | `coinank/market-order/agg-cvd exchanges= symbol=BTCUSDT interval=1h size=24` |
| "Buy/sell pressure on BTC across all exchanges?" | `coinank/market-order/agg-buy-sell-value exchanges= symbol=BTCUSDT interval=1h size=24` |
| "Show the BTC order book depth" | `coinank/orderbook/by-symbol exchange=Binance symbol=BTCUSDT interval=1h size=24` |
| "What's the current BTC price?" | `coinank/price/last symbol=BTCUSDT exchange=Binance productType=SWAP` |
| "Show BTC 1-hour candles" | `coinank/kline/lists symbol=BTCUSDT exchange=Binance interval=1h size=100` |
| "Top gainers today?" | `nofx/price/ranking duration=24h` (top) |
| "Top losers today?" | `nofx/price/ranking duration=24h` (bottom) |
| "What's the volume ranking?" | `coinank/rank/volume sortBy=h24Volume sortType=desc` |
| "Coins with overbought RSI?" | `coinank/rsi/list` |
| "What's trending on Upbit?" | `nofx/upbit/hot limit=20` |
| "Korean market inflows?" | `nofx/upbit/netflow/top-ranking limit=20 duration=1h` |
| "What are people searching for in crypto?" | `nofx/query-rank/list limit=20` |
| "Latest crypto news" | `coinank/news/list type=2 lang=en page=1 pageSize=10` |
| "Latest crypto flash alerts" | `coinank/news/list type=1 lang=en page=1 pageSize=20` |
| "What coins can I look up?" | `coinank/coin/list` |
| "What trading pairs does Binance support?" | `coinank/coin/symbols exchange=Binance` |

---

## Complete Endpoint Reference (96 endpoints)

### 🤖 AI Trading Signals

| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/nofx/ai500/list` | AI500 high-potential coins (AI Score > 70) | `limit` |
| `/api/v1/nofx/ai500/stats` | AI500 index statistics & signal distribution | — |
| `/api/v1/nofx/ai300/list` | AI300 quant model rankings (fund flow strength) | `limit` |
| `/api/v1/nofx/ai300/stats` | AI300 model statistics | — |
| `/api/v1/nofx/netflow/top-ranking` | Top net capital inflow coins | `limit`, `duration`, `type`, `trade` |
| `/api/v1/nofx/netflow/low-ranking` | Top net capital outflow coins | `limit`, `duration`, `type`, `trade` |
| `/api/v1/nofx/oi/top-ranking` | Biggest open interest increase coins | `limit`, `duration` |
| `/api/v1/nofx/oi/low-ranking` | Biggest open interest decrease coins | `limit`, `duration` |
| `/api/v1/nofx/price/ranking` | Price change rankings — gainers & losers | `duration` |
| `/api/v1/nofx/long-short/list` | Long/short ratio anomaly coins | `limit` |
| `/api/v1/nofx/funding-rate/top` | Highest positive funding rate coins | `limit` |
| `/api/v1/nofx/funding-rate/low` | Most negative funding rate coins | `limit` |
| `/api/v1/nofx/oi-cap/ranking` | Open interest / market cap rankings | `limit` |
| `/api/v1/nofx/upbit/hot` | Upbit hot coins by trading volume | `limit` |
| `/api/v1/nofx/upbit/netflow/top-ranking` | Upbit net inflow rankings | `limit`, `duration` |
| `/api/v1/nofx/upbit/netflow/low-ranking` | Upbit net outflow rankings | `limit`, `duration` |
| `/api/v1/nofx/heatmap/list` | Order book heatmap overview | `trade`, `limit` |
| `/api/v1/nofx/query-rank/list` | Most searched coin rankings today | `limit` |

**`duration` values:** `5m` `15m` `1h` `4h` `24h`

---

### 📈 Market Data

#### Coin Reference
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/coin/list` | Full supported coin list | — |
| `/api/v1/coinank/coin/market-cap` | Coin market cap info | `baseCoin` |
| `/api/v1/coinank/coin/symbols` | Supported trading pairs by exchange | `exchange` |

#### Price & Candlesticks
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/price/last` | Real-time latest price | `symbol`, `exchange`, `productType` |
| `/api/v1/coinank/kline/lists` | OHLCV candlestick data | `symbol`, `exchange`, `interval`, `size`, `endTime` |

#### ETF Flows
| Endpoint | Description |
|----------|-------------|
| `/api/v1/coinank/etf/us-btc` | US Bitcoin ETF list (IBIT, FBTC, ARKB, etc.) |
| `/api/v1/coinank/etf/us-eth` | US Ethereum ETF list |
| `/api/v1/coinank/etf/us-btc-inflow` | US BTC ETF historical net inflow |
| `/api/v1/coinank/etf/us-eth-inflow` | US ETH ETF historical net inflow |
| `/api/v1/coinank/etf/hk-inflow` | Hong Kong crypto ETF net inflow |

#### Fund Flow
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/fund/realtime` | Real-time fund flow rankings | `sortBy` (h1net/h4net/h24net), `productType`, `page`, `size` |
| `/api/v1/coinank/fund/history` | Historical fund flow by coin | `baseCoin`, `endTime`, `productType`, `size`, `interval` |

#### Open Interest
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/oi/all` | Real-time OI breakdown by exchange | `baseCoin` |
| `/api/v1/coinank/oi/by-exchange` | OI breakdown by exchange (chart) | `baseCoin` |
| `/api/v1/coinank/oi/agg-chart` | Aggregated OI history | `baseCoin`, `exchange`, `interval`, `size`, `endTime` |
| `/api/v1/coinank/oi/symbol-chart` | OI history by trading pair | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/oi/kline` | OI candlestick | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/oi/agg-kline` | Aggregated OI candlestick | `baseCoin`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/oi/vs-market-cap-hist` | OI / market cap ratio history | `baseCoin`, `endTime`, `size`, `interval` |

#### Liquidations
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/liquidation/orders` | Recent liquidation order list | `baseCoin`, `exchange`, `side`, `amount`, `endTime` |
| `/api/v1/coinank/liquidation/intervals` | Liquidation stats by time period | `baseCoin` |
| `/api/v1/coinank/liquidation/agg-history` | Aggregated liquidation history | `baseCoin`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/liquidation/history` | Liquidation history by trading pair | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/liquidation/liq-map` | Liquidation map (price-level clusters) | `symbol`, `exchange`, `interval` |
| `/api/v1/coinank/liquidation/heat-map` | Liquidation heatmap | `exchange`, `symbol`, `interval` |
| `/api/v1/coinank/liquidation/agg-liq-map` | Aggregated liquidation map (VIP4) | `symbol`, `exchange`, `interval` |
| `/api/v1/coinank/liquidation/heat-map-symbols` | Supported symbols for liq heatmap | — |

#### Long/Short Ratios
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/longshort/realtime` | Real-time L/S ratio by exchange | `baseCoin`, `interval` |
| `/api/v1/coinank/longshort/buy-sell` | Global buy-sell L/S ratio history | `baseCoin`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/longshort/person` | Account-level L/S ratio | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/longshort/position` | Whale position-level L/S ratio | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/longshort/account` | Whale account L/S ratio (VIP1) | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/longshort/kline` | L/S ratio candlestick (VIP1) | `type` (longShortPerson/longShortPosition/longShortAccount), `exchange`, `symbol`, `interval`, `endTime`, `size` |

#### Funding Rates
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/funding-rate/current` | Real-time funding rate rankings | `type` (current/day/week/month/year) |
| `/api/v1/coinank/funding-rate/accumulated` | Accumulated funding rate cost | `type` (current/day/week/month/year) |
| `/api/v1/coinank/funding-rate/hist` | Historical funding rates by coin | `baseCoin`, `exchangeType`, `endTime`, `size` |
| `/api/v1/coinank/funding-rate/weighted` | Weighted average funding rate | `baseCoin`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/funding-rate/heatmap` | Funding rate heatmap | `type` (openInterest/marketCap), `interval` |
| `/api/v1/coinank/funding-rate/indicator` | Funding rate history by pair (VIP1) | `exchange`, `symbol`, `endTime`, `size` |
| `/api/v1/coinank/funding-rate/kline` | Funding rate candlestick (VIP1) | `exchange`, `symbol`, `interval`, `endTime`, `size` |

#### Rankings & Screeners
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/rank/screener` | Multi-dimensional visual screener | `interval` |
| `/api/v1/coinank/rank/oi` | OI amount rankings | `sortBy`, `sortType`, `size`, `page` |
| `/api/v1/coinank/rank/long-short` | L/S ratio rankings | `sortBy`, `sortType`, `size`, `page` |
| `/api/v1/coinank/rank/liquidation` | Liquidation amount rankings | `sortBy`, `sortType`, `page`, `size` |
| `/api/v1/coinank/rank/volume` | Trading volume rankings | `sortBy`, `sortType` |
| `/api/v1/coinank/rank/price` | Price change rankings | `sortBy`, `sortType` |
| `/api/v1/coinank/rank/oi-vs-market-cap` | OI / market cap ratio rankings (VIP2) | `sortBy`, `sortType`, `size`, `page` |
| `/api/v1/coinank/rank/trade-count` | Trade count rankings (VIP2) | `sortBy` (h1Count/h4Count/d1Count), `sortType` |
| `/api/v1/coinank/rsi/list` | RSI screener | `interval` (1H/4H/1D — uppercase) |

#### Whale Activity
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/hyper/top-position` | HyperLiquid whale position rankings | `sortBy`, `sortType`, `page`, `size` |
| `/api/v1/coinank/hyper/top-action` | HyperLiquid latest whale trade actions | — |
| `/api/v1/coinank/trades/large` | Large market orders (block trades) | `symbol`, `productType`, `amount`, `endTime`, `size` |
| `/api/v1/coinank/big-order/list` | Large limit orders in order book | `symbol`, `exchangeType`, `size`, `amount`, `side` |
| `/api/v1/coinank/net-positions` | Net long/short position history | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/order-flow/lists` | Order flow delta data | `exchange`, `symbol`, `interval`, `endTime`, `size` |

#### Taker Flow & Market Microstructure
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/market-order/cvd` | CVD — cumulative taker delta (single pair, VIP3) | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/market-order/buy-sell-count` | Taker trade count by direction (VIP3) | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/market-order/buy-sell-value` | Taker buy/sell value USD (VIP3) | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/market-order/buy-sell-volume` | Taker buy/sell volume coin (VIP3) | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/market-order/agg-cvd` | Aggregated CVD cross-exchange (VIP3) | `exchanges` (empty=all), `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/market-order/agg-buy-sell-count` | Aggregated trade count cross-exchange (VIP3) | `exchanges`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/market-order/agg-buy-sell-value` | Aggregated buy/sell value cross-exchange (VIP3) | `exchanges`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/market-order/agg-buy-sell-volume` | Aggregated buy/sell volume cross-exchange (VIP3) | `exchanges`, `symbol`, `interval`, `endTime`, `size` |

#### Order Book Depth
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/orderbook/by-symbol` | Order book depth history by pair (VIP3) | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/orderbook/by-exchange` | Order book depth history by exchange (VIP3) | `exchange`, `symbol`, `interval`, `endTime`, `size` |
| `/api/v1/coinank/orderbook/heatmap` | Order book liquidity heatmap (VIP4) | `exchange`, `symbol`, `interval`, `endTime` (must be current timestamp) |

#### Market Cycle Indicators
| Endpoint | Description |
|----------|-------------|
| `/api/v1/coinank/indicator/fear-greed` | Crypto fear & greed index (0=extreme fear, 100=extreme greed) |
| `/api/v1/coinank/indicator/altcoin-season` | Altcoin Season Index (>75 = altcoin season) |
| `/api/v1/coinank/indicator/btc-multiplier` | BTC 2-year moving average multiplier |
| `/api/v1/coinank/indicator/btc-pi` | Pi Cycle Top indicator |
| `/api/v1/coinank/indicator/ahr999` | AHR999 Bitcoin accumulation indicator |
| `/api/v1/coinank/indicator/puell-multiple` | Puell Multiple (miner revenue / 365-day MA) |
| `/api/v1/coinank/indicator/grayscale` | Grayscale holdings (GBTC/ETHE) |
| `/api/v1/coinank/indicator/charts` | Composite charts (rainbow, etc.) |
| `/api/v1/coinank/indicator/ma-heatmap` | 200-week moving average heatmap |
| `/api/v1/coinank/indicator/market-cap-rank` | Coin market cap share rankings |

#### News & Flash Alerts
| Endpoint | Description | Key Params |
|----------|-------------|------------|
| `/api/v1/coinank/news/list` | News and flash bulletins | `type` (1=flash, 2=news), `lang` (zh/en), `page`, `pageSize` |
| `/api/v1/coinank/news/detail` | Full article by ID | `id` |

---

## Parameter Reference

| Parameter | Values / Format |
|-----------|-----------------|
| `exchange` | `Binance` `OKX` `Bybit` `Bitget` `dYdX` |
| `productType` | `SWAP` (perpetual futures) · `SPOT` |
| `interval` | `1m` `5m` `15m` `1h` `4h` `1d` |
| `duration` (nofx) | `5m` `15m` `1h` `4h` `24h` |
| `endTime` | Unix timestamp in **milliseconds** — use `Date.now()` if omitted |
| `size` | Number of data points to return (default varies, max ~500) |
| `sortType` | `asc` or `desc` |
| `lang` (news) | `en` (English) · `zh` (Chinese) |
| `type` (news) | `1` = flash alert · `2` = news article |
| RSI `interval` | **Uppercase**: `1H` `4H` `1D` |

---

## Tips for Best Results

- **Always use `Date.now()` for `endTime`** when fetching real-time or recent historical data.
- **Combine endpoints** for richer analysis: e.g., high funding rate + rising OI + net inflow often signals a leveraged long squeeze setup.
- **`exchanges=""` (empty string)** in market-order agg endpoints means aggregate across all exchanges.
- **VIP1/2/3/4 endpoints** are accessible through claw402 like all others — no extra configuration needed.
- **Free catalog**: `https://claw402.ai/api/v1/catalog` — always up to date, no payment required.
- **Present results clearly**: use tables or bullet points, not raw JSON. Highlight the most actionable numbers.

---

*Powered by [claw402.ai](https://claw402.ai) — x402 micropayment gateway for AI agents.*
