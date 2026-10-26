# Example Field sheet: $USELESS

> A real Assay, rebuilt from the evidence pack in [`pack-sample.json`](pack-sample.json).
> **Mint:** `Dz9mQ9NzkBcCsuGPFJ3r1bS4wgqKMHBPiVuniW8Mbonk` (USELESS COIN, Solana)
> **Collected:** 2026-10-25 13:36 UTC. Numbers are a snapshot. Research, not financial advice.

---

## Field sheet — $USELESS (USELESS COIN)
`Dz9mQ9NzkBcCsuGPFJ3r1bS4wgqKMHBPiVuniW8Mbonk` · Solana · slot `461276465` · collected 2026-10-25 13:36 UTC

**Headline:** A clean, renounced SPL mint with deep exits. The only real weight is holder concentration.
**Summary:** Every authority over the mint is set to none, so supply is fixed and no account can be frozen. The main Raydium CPMM pool holds about $4.2M against $1.5M in 24h volume, and the provider raised no checks.
**Main catch:** The top ordinary holders in the sample control 36.48% of supply, and one wallet alone holds 8.96%.
**What to watch:**
- Movement from the largest ordinary wallet (8.96%), which could exit into a $4.2M pool
- Whether buys keep leading sells (4,970 / 3,419) after a +9.68% day

### Entry risk · **B**
18 of 100 risk points, from factors actually read. Higher letters are riskier.

| Metric | Value |
| --- | --- |
| Pool liquidity | $4,202,446 |
| 24h volume | $1,508,969 |
| Holders reported | 234,119 |
| 24h buys / sells | 4,970 / 3,419 |

### Risk bands
| Band | Points | Reading |
| --- | --- | --- |
| Token powers | `░░░░░░░░░░` 0 / 36 | No power over somebody else's balance was found |
| Holder concentration | `███████░░░` 18 / 26 | Top sample holders hold 36.48%; 2.38% in pools and 5.35% in lockers set aside |
| Liquidity & exit room | `░░░░░░░░░░` 0 / 20 | Deepest pool returned holds $4,202,446 |
| Provider-reported checks | `░░░░░░░░░░` 0 / 18 | RugCheck raised none of its checks; LP 100% locked |

### Crew notes
- **Slate** (Identity & origin) — A live SPL token on Solana calling itself USELESS COIN ($USELESS), with name and symbol matching across chain and provider.
- **Clasp** (Contract powers) — Mint and freeze authorities are none, with no transfer hook, fee, or delegate, so nobody can change your balance but you.
- **Gauge** (Liquidity & exits) — The deepest exit is the Raydium CPMM USELESS/SOL pool at about $4.2M, out of 30 pools returned.
- **Tare** (Supply & burn) — Supply is fixed at about 999.08M, and a negligible ~0.0% sits at the incinerator. Burns on Solana also leave the supply figure itself.
- **Sift** (Holders & control) — 92 of the top 100 are ordinary wallets holding 36.48%, and the largest holds 8.96%. *(written by Crucible from holders sample)*
- **Pulse** (Trading activity) — 8,389 trades in 24h in the Raydium CPMM pool, with buys leading sells 4,970 to 3,419.

### Market conditions
**Continuation**: price up 9.68% on the day, with buys outnumbering sells by about 1.45×.
