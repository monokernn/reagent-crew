# Room protocol: how an Assay runs

This is how the REAGENT Crew room behaves. Every agent prompt in [`../agents/`](../agents/) follows these rules.

## Roles

| Who | Does | Never does |
| --- | --- | --- |
| **Crucible** (lead) | Collects the evidence pack once, posts the Field sheet, and fills any missing crew lines | Waits on specialists, mixes mints, invents a grade |
| **Slate · Clasp · Gauge · Tare · Pulse** | Each posts one 1–2 sentence English note on its own beat | Fetches chain data, talks to other agents, invents facts |
| **Sift** | One holders note when present | Often absent (6-member room limit). Crucible covers the line |
| **Docket** | One docs/RWA note when asked | Is not one of the six Field sheet lines |

## The flow

```
you ──▶ "Assay <mint>"
          │
          ▼
  Crucible: collect ONE evidence pack for <mint>   (scripts, not agents)
          │
          ├──▶ Crucible posts the Field sheet IMMEDIATELY (markdown, in the room)
          │        └─ writes any crew line that is missing or for the wrong mint
          │
          └──▶ Specialists each post ONE note for <mint> from their slice
                   └─ a missing field becomes a gap note, which counts as a result
```

1. **Trigger.** Someone types `Assay <mint>` to Crucible in the Crew room.
2. **One shared pack.** Crucible collects evidence for **that mint only**, one time, by script. In production that is `reagent.agents.collect` + `rate` from [monokernn/REAGENT](https://github.com/monokernn/REAGENT). Agents never fetch chain data on their own.
3. **Fail-closed Field sheet.** Crucible posts the final [Field sheet](field-sheet.md) right away and **does not wait** for specialist notes. If a crew line is missing, late, or for a different mint, Crucible writes it from the pack. A band that could not be read is withheld with the reason, never guessed.
4. **Specialist notes.** Each specialist posts **exactly one** note, labeled with its name and beat, for the current mint. It does not stay silent, and it does not say "already posted" when its last note was for a different mint. A wrap-up line like "reply only if essential" does not apply while an Assay for a mint is open and the agent has not posted for that mint.
5. **Done.** The room holds one Field sheet and up to six notes, all for the same mint.

## Hard rules (all agents)

- **Never mix mints.** Each sheet and each note covers one mint only.
- **English only** in sheets and notes.
- **No wallet, signature, or transaction.** The desk reads data and never acts on chain.
- **Never invent a grade or a fact.** Grades come from the rating engine. Facts come from the pack.
- **A gap is a result.** "The pack had no pool liquidity, so a declared pool would have answered this" is a valid note.
- **No bubble maps.** The sheet is text, tables, and unicode bars only.
- **Sift may be absent.** With six members in the room, Crucible writes the Sift line from the holders sample and labels it.

## Room setup

A Grok Bot room holds **6 members**. The recommended Crew room is:

`You · Crucible · Slate · Clasp · Gauge · Tare · Pulse`. If your room counts you inside the limit, leave one specialist out and Crucible will write that line.

Keep Sift and Docket outside the room and talk to them 1:1 when you need a deeper holders or docs read. See [`../../scripts/spawn-checklist.md`](../../scripts/spawn-checklist.md).
