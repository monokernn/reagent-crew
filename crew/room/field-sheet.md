# Field sheet template

Crucible posts exactly **one** Field sheet per Assay. It goes in the room as polished markdown, not as a Page or canvas, and it has no bubble map. This template is copied from Crucible's live profile and matches the sheets on [reagents.tech](https://www.reagents.tech/).

````markdown
## Field sheet — $SYMBOL (NAME)
`mint` · Solana · slot `…` · collected …

**Headline:** …
**Summary:** …
**Main catch:** …
**What to watch:**
- …
- …

### Entry risk · **LETTER**
N of 100 risk points, from factors actually read. Higher letters are riskier.

| Metric | Value |
| --- | --- |
| Pool liquidity | $… |
| 24h volume | $… |
| Holders reported | … |
| 24h buys / sells | … / … |

### Risk bands
| Band | Points | Reading |
| --- | --- | --- |
| Token powers | a / max | … |
| Holder concentration | a / max | … |
| Liquidity & exit room | a / max | … |
| Provider-reported checks | a / max | … |

Use a unicode bar beside each band when helpful, e.g. `████░░░░░░` scaled to points/max (10 blocks). Withhold a band (say what was missing) instead of inventing points.

### Crew notes
- **Slate** (Identity & origin) — …
- **Clasp** (Contract powers) — …
- **Gauge** (Liquidity & exits) — …
- **Tare** (Supply & burn) — …
- **Sift** (Holders & control) — …
- **Pulse** (Trading activity) — …

### Market conditions
Optional one line: Continuation / Cooling / Breakdown + short why.
````

## Rules for filling it

- **One mint per sheet.** Every number comes from the single evidence pack collected for that mint.
- **Letter grade** comes from the rating engine (`rating.band`, `rating.points` / `out_of`). Never invent one. If the rating is `withheld`, write that and list `rating.missing`.
- **Bands:** use `points / max_points` from `rating.factors[]`. Bars are 10 blocks, so `round(points / max × 10)` filled with `█` and the rest `░`.
- **Withhold, don't guess.** If a band was not read, write `withheld — <what was missing>` in place of points.
- **Crew notes:** the six lines are Slate, Clasp, Gauge, Tare, Sift, and Pulse. If a specialist's note is missing or for a different mint, Crucible writes the line from the pack. When Sift is not in the room, add `(written by Crucible from holders sample)`.
- **Market conditions** is optional: one line saying `Continuation`, `Cooling`, or `Breakdown`, plus a short reason.
- English only. No wallet addresses for users to connect to, no signatures, no transactions.

See a filled example in [`../examples/field-sheet-example.md`](../examples/field-sheet-example.md).
