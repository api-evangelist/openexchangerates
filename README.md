# Open Exchange Rates (openexchangerates)

Open Exchange Rates provides a simple, reliable REST API for live and historical foreign exchange (forex) rates covering 200+ world currencies, with end-of-day historical data back to January 1st, 1999. The JSON API delivers latest rates, historical snapshots, bulk time-series, currency conversion, and OHLC data over HTTPS from `https://openexchangerates.org/api`.

Access requires a free account and an **App ID** (`app_id`), passed as a query parameter or an `Authorization: Token` header on every request. Pricing is published in monthly tiers: a Free plan (1,000 requests/month, hourly updates, USD base only), Developer ($12/month, 10,000 requests, all base currencies), Enterprise ($47/month, 100,000 requests, 30-minute updates, time-series), Unlimited ($97/month, unlimited requests, 5-minute updates, conversion), and custom VIP levels (up to 1-second updates, bid-ask, OHLC, intra-day historical). Feature availability is tiered - changing the base currency requires a paid plan, time-series requires Enterprise or above, convert requires Unlimited, and OHLC is VIP Platinum only. The `currencies.json` and `usage.json` endpoints are free and do not count against your quota.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/openexchangerates/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/openexchangerates/refs/heads/main/apis.yml)

## Tags

- Foreign Exchange
- Currency
- Exchange Rates
- FX
- Currency Conversion
- Forex
- Financial Data

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Open Exchange Rates Latest Rates API

Get the latest exchange rates for 200+ world currencies from `GET /latest.json`, relative to a base currency (USD by default; changing the base requires a paid plan). Rates refresh hourly on the Free and Developer plans, every 30 minutes on Enterprise, and every 5 minutes on Unlimited.

- **Human URL:** [https://docs.openexchangerates.org/reference/latest-json](https://docs.openexchangerates.org/reference/latest-json)
- **Base URL:** `https://openexchangerates.org/api`

#### Tags

- Foreign Exchange
- Exchange Rates
- Live Rates

#### Properties

- [Documentation](https://docs.openexchangerates.org/reference/api-introduction)
- [API Reference](https://docs.openexchangerates.org/reference/latest-json)
- [OpenAPI](openapi/openexchangerates-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openexchangerates.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openexchangerates.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Exchange Rates Historical Rates API

Get end-of-day foreign exchange rates for any UTC date back to January 1st, 1999 from `GET /historical/{date}.json`. Base currency and symbols filtering are available on the Developer, Enterprise, and Unlimited plans.

- **Human URL:** [https://docs.openexchangerates.org/reference/historical-json](https://docs.openexchangerates.org/reference/historical-json)
- **Base URL:** `https://openexchangerates.org/api`

#### Tags

- Foreign Exchange
- Historical Rates
- Exchange Rates

#### Properties

- [API Reference](https://docs.openexchangerates.org/reference/historical-json)
- [OpenAPI](openapi/openexchangerates-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openexchangerates.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openexchangerates.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Exchange Rates Time Series API

Get bulk daily historical exchange rates for a given start and end date (maximum one month per query) from `GET /time-series.json`. Each day in the range counts as one API request. Available on the Enterprise and Unlimited plans.

- **Human URL:** [https://docs.openexchangerates.org/reference/time-series-json](https://docs.openexchangerates.org/reference/time-series-json)
- **Base URL:** `https://openexchangerates.org/api`

#### Tags

- Foreign Exchange
- Time Series
- Exchange Rates

#### Properties

- [API Reference](https://docs.openexchangerates.org/reference/time-series-json)
- [OpenAPI](openapi/openexchangerates-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openexchangerates.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openexchangerates.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Exchange Rates Convert API

Convert any monetary value from one currency to another at the latest API rates via `GET /convert/{value}/{from}/{to}`, returning the exchange rate used, the timestamp, and the converted amount. Available on the Unlimited plan.

- **Human URL:** [https://docs.openexchangerates.org/reference/convert](https://docs.openexchangerates.org/reference/convert)
- **Base URL:** `https://openexchangerates.org/api`

#### Tags

- Currency Conversion
- Foreign Exchange
- FX

#### Properties

- [API Reference](https://docs.openexchangerates.org/reference/convert)
- [OpenAPI](openapi/openexchangerates-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openexchangerates.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openexchangerates.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Exchange Rates Currencies API

Get the list of all currency symbols available through the API as a JSON map of 3-letter codes to full currency names from `GET /currencies.json`, with options to include alternative, digital, and inactive currencies. Requests to this endpoint do not count against your usage quota.

- **Human URL:** [https://docs.openexchangerates.org/reference/currencies-json](https://docs.openexchangerates.org/reference/currencies-json)
- **Base URL:** `https://openexchangerates.org/api`

#### Tags

- Currency
- Reference Data
- ISO 4217

#### Properties

- [API Reference](https://docs.openexchangerates.org/reference/currencies-json)
- [OpenAPI](openapi/openexchangerates-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openexchangerates.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openexchangerates.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Exchange Rates OHLC API

Get open, high, low, close, and time-weighted average exchange rates for a given period (1m to 1mo) from `GET /ohlc.json`, with data available from December 19th, 2016. Restricted to the VIP Platinum tier.

- **Human URL:** [https://docs.openexchangerates.org/reference/ohlc-json](https://docs.openexchangerates.org/reference/ohlc-json)
- **Base URL:** `https://openexchangerates.org/api`

#### Tags

- OHLC
- Foreign Exchange
- Market Data

#### Properties

- [API Reference](https://docs.openexchangerates.org/reference/ohlc-json)
- [OpenAPI](openapi/openexchangerates-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openexchangerates.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openexchangerates.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Exchange Rates Usage API

Get plan information and usage statistics for your App ID from `GET /usage.json` - account status, plan name, quota, update frequency, enabled features, requests made, requests remaining, and daily average. Requests to this endpoint do not count against your usage quota.

- **Human URL:** [https://docs.openexchangerates.org/reference/usage-json](https://docs.openexchangerates.org/reference/usage-json)
- **Base URL:** `https://openexchangerates.org/api`

#### Tags

- Usage
- Account
- Quotas

#### Properties

- [API Reference](https://docs.openexchangerates.org/reference/usage-json)
- [OpenAPI](openapi/openexchangerates-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openexchangerates.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openexchangerates.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/openexchangerates)
- [LinkedIn](https://www.linkedin.com/company/open-exchange-rates)
- [Website](https://openexchangerates.org)
- [Documentation](https://docs.openexchangerates.org)
- [Pricing](https://openexchangerates.org/signup)
- [Plans](plans/openexchangerates-plans-pricing.yml)
- [Rate Limits](rate-limits/openexchangerates-rate-limits.yml)
- [Fin Ops](finops/openexchangerates-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
