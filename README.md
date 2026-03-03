# claw402-open

Public resources for [claw402.ai](https://claw402.ai) — the universal x402 API payment gateway.

Pay-per-call access to 200+ premium APIs using USDC micropayments on Base. No API key signup, no subscription — just connect a wallet and call.

## What's Here

```
providers/          # API provider definitions (YAML)
logos/              # Provider logo SVGs
openclaw-skill/     # OpenClaw AI agent skill
docs/               # Public documentation
```

## Providers

Each YAML file in `providers/` defines an API provider and its endpoints. These are the source of truth for what's available on the claw402 marketplace.

| Provider | Category | Endpoints | Price/Call |
|----------|----------|-----------|------------|
| [CoinAnk](https://coinank.com) | Crypto | 59 | $0.00001 |
| [NoFXOS](https://nofx.ai) | AI Signals | 18 | $0.00001 - $0.001 |
| [Polygon.io](https://polygon.io) | US Stocks | 25 | $0.00001 |
| [Alpha Vantage](https://alphavantage.co) | US Stocks | 27 | $0.00001 |
| [Alpaca](https://alpaca.markets) | US Stocks | 10 | $0.00001 |
| [Twelve Data](https://twelvedata.com) | Multi-Asset | 15 | $0.00001 |
| [Tushare](https://tushare.pro) | A-Shares | 10 | $0.00001 |
| [OpenAI](https://openai.com) | AI Models | 3 | $0.01 - $0.025 |
| [Anthropic](https://anthropic.com) | AI Models | 3 | $0.01 - $0.025 |

## Submit Your API

Want to list your API on claw402? Create a provider YAML file and submit a Pull Request.

### Quick Start

1. Copy the template below to `providers/your-api.yaml`
2. Fill in your provider details and endpoint definitions
3. Submit a PR to this repo
4. We review and activate your provider on the marketplace
5. Start earning USDC per API call

### Provider YAML Template

```yaml
id: your-api                    # Unique slug (lowercase, hyphens only)
name: Your API Name
short_description: "Brief description of your API"
full_description: "Detailed description of what your API provides"
website: https://your-api.com
logo_url: /providers/your-api.svg    # Add your logo to logos/
category: crypto                     # crypto | stocks | forex | ai | cn_stocks
tags: [tag1, tag2, tag3]
featured: false

# Upstream configuration (how claw402 connects to your API)
upstream_base_url: https://api.your-service.com
upstream_type: api_key               # api_key | query_param
upstream_auth_env: YOUR_API_KEY      # Environment variable name for your API key
upstream_auth_header: Authorization  # Header name (for api_key type)
# upstream_auth_query: apikey        # Query param name (for query_param type)

routes:
  # Each route becomes a paid endpoint on claw402.ai
  - gateway_path: /api/v1/your-api/endpoint-name
    upstream_path: /v2/your-upstream-path
    category: Data Category
    user_price: "0.00001"            # Price in USDC per call
    description: "Endpoint description (Chinese)"
    description_en: "Endpoint description (English)"
    method: GET                      # GET or POST
    allowed_params: [param1, param2] # Query params users can pass

  # Path parameters are supported with {placeholder} syntax
  - gateway_path: /api/v1/your-api/item
    upstream_path: /v2/items/{itemId}
    category: Items
    user_price: "0.00001"
    description_en: "Get item by ID"
    method: GET
    allowed_params: [itemId]
```

### Logo Requirements

- Format: SVG
- Size: 200x200px viewBox recommended
- Dark background compatible (will be displayed on dark UI)
- Place in `logos/your-api.svg`

### Pricing Guidelines

- Micro-data endpoints (price quotes, simple lookups): `$0.00001` per call
- Standard data endpoints (historical data, analytics): `$0.00001 - $0.0001`
- AI/ML inference endpoints: `$0.001 - $0.025` per call
- You set the price, platform takes a commission on each call

### Review Process

1. **Automated checks**: YAML syntax, required fields, no duplicate paths
2. **Manual review**: Endpoint descriptions, pricing reasonableness, API reliability
3. **Activation**: Routes go live on claw402.ai marketplace
4. **Revenue**: You earn USDC per API call, settled periodically

## OpenClaw Skill

The `openclaw-skill/` directory contains the AI agent skill for [OpenClaw](https://openclaw.ai). This allows any AI agent to access claw402 APIs with a single wallet.

```bash
# Install in OpenClaw
clawhub install claw402
```

## SDKs

- **TypeScript**: [github.com/NoFxAiOS/claw402-js](https://github.com/NoFxAiOS/claw402-js)
- **Python**: [github.com/NoFxAiOS/claw402-python](https://github.com/NoFxAiOS/claw402-python)
- **Go**: [github.com/NoFxAiOS/claw402-go](https://github.com/NoFxAiOS/claw402-go)

## Links

- Website: [claw402.ai](https://claw402.ai)
- Marketplace: [claw402.ai/marketplace](https://claw402.ai/marketplace)
- x402 Protocol: [x402.org](https://x402.org)

## License

MIT
