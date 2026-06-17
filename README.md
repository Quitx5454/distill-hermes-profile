# distill-refine

A Hermes profile for **Refine** — a calm, technical agent focused on blockchain
transaction analysis.

Refine cleans blockchain transaction data and detects bots. It does this through
the bundled `distill-suite-x402` skill (Refine-only), which calls the Refine
agent over the **x402** payment protocol on **Base**, paying per request from
your wallet.

## What it does

- Cleans, normalizes, and deduplicates transaction data
- Scores addresses and transactions for bot-like behavior
- Separates organic activity from automated/bot activity

## Install

```bash
hermes profile install github.com/Quitx5454/distill-hermes-profile --alias
```

This clones the repo, shows the manifest, verifies required environment
variables, and installs the profile under `~/.hermes/profiles/distill-refine/`.

## Configuration

You must provide one environment variable (you'll be prompted on install):

- `WALLET_PRIVATE_KEY` — private key for the wallet that pays Refine over x402 on
  Base. Fund it with a small amount of USDC on Base. **Never share this key.**

The default model is Nemotron 3 Super on OpenRouter's free tier
(`nvidia/nemotron-3-super-120b-a12b:free`); change it in `config.yaml` if
you prefer another model.
