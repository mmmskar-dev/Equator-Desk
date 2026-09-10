# Equator Desk

A demo trading terminal with two pages:

1. **P2P arbitrage** — a currency ticker (KES, UGX, TZS, GBP, EUR, USDT, JPY, NGN), side-by-side Binance/OKX P2P order-book tables with payment-method filtering and price sorting, and an advisory panel that ranks arbitrage opportunities by spread.
2. **Futures bot** — 25 crypto assets with a simulated directional-confidence score, and an auto-trading engine you configure (paper portfolio size, number of active trades, capital allocation, risk preference) that opens and closes simulated positions on its own.

## Important: this is a simulation

- Market data (P2P order books, FX rates, and futures prices) is **generated locally** with a randomized model — it is **not** pulled from real Binance/OKX accounts or feeds.
- Login is a **local, in-memory mock** — there is no backend, database, or credential storage.
- The futures bot only trades an in-memory paper balance. It never places real orders.
- To go from demo to production you would need: a backend with encrypted credential storage and real auth (e.g. OAuth or a hashed-password + session/JWT flow), signed requests to the Binance/OKX REST or WebSocket APIs (with your own API keys, kept server-side), a real strategy/signal engine, and — if you ever move to live trading — regulatory and risk-management review appropriate to your jurisdiction.

## Run locally

```bash
npm install
npm run dev
```

Then open the printed local URL (typically http://localhost:5173).

To build a production bundle:

```bash
npm run build
npm run preview
```

## Structure

- `src/App.jsx` — the entire app (login, P2P page, futures page, mock data engine)
- `src/main.jsx` — React entry point
- `index.html` — Vite HTML shell
