# Spawn checklist: rebuild the desk in about 15 minutes

Follow these steps in order. Each one is small.

## 0 · Prereqs
1. A Grok Bot account (or Cursor, if you run agents there).
2. Clone this repo: `git clone <this-repo> && cd Reagent-Crew`
3. Optional: an evidence collector. Production uses [monokernn/REAGENT](https://github.com/monokernn/REAGENT) (assayer). Any script works if it outputs the shape in [`crew/examples/pack-sample.json`](../crew/examples/pack-sample.json).

## 1 · Sidebar section
4. In the Grok Bot sidebar, create a section named **REAGENT**.
5. Everything below goes into that section, so the desk stays together.

## 2 · Spawn the eight bots
For each file, create a new bot, set the **name** to the file's title, and paste the block under *Paste as agent description* as the description:

6. [ ] **Crucible** ← [`crew/agents/crucible.md`](../crew/agents/crucible.md) *(spawn first: it is the lead)*
7. [ ] **Slate** ← [`crew/agents/slate.md`](../crew/agents/slate.md)
8. [ ] **Clasp** ← [`crew/agents/clasp.md`](../crew/agents/clasp.md)
9. [ ] **Gauge** ← [`crew/agents/gauge.md`](../crew/agents/gauge.md)
10. [ ] **Tare** ← [`crew/agents/tare.md`](../crew/agents/tare.md)
11. [ ] **Pulse** ← [`crew/agents/pulse.md`](../crew/agents/pulse.md)
12. [ ] **Sift** ← [`crew/agents/sift.md`](../crew/agents/sift.md)
13. [ ] **Docket** ← [`crew/agents/docket.md`](../crew/agents/docket.md)
14. Move all eight into the **REAGENT** section.

## 3 · Open the Crew room
15. Create a group room named **REAGENT Crew**.
16. Add **Crucible, Slate, Clasp, Gauge, Tare, Pulse** (6-member limit). If your room counts you toward the limit, drop one specialist. Crucible will write that line.
17. Leave **Sift** and **Docket** out and use them 1:1 for deeper holders or docs reads.

## 4 · Give Crucible evidence
18. **With assayer:** set up [monokernn/REAGENT](https://github.com/monokernn/REAGENT) where Crucible can run it (`reagent.agents.collect` / `rate`).
19. **Without it:** paste a pack in the same shape as [`pack-sample.json`](../crew/examples/pack-sample.json) into the room, or edit step 1 of Crucible's prompt to point at your own collector.

## 5 · First Assay
20. In the Crew room, type: `Assay <mint>`
21. Check that:
    - [ ] Crucible posted **one** markdown Field sheet right away, without waiting on notes
    - [ ] The sheet matches [`crew/room/field-sheet.md`](../crew/room/field-sheet.md)
    - [ ] Every number belongs to the same mint
    - [ ] Each specialist posted at most one labeled English note
    - [ ] Sift's line is marked as written by Crucible if Sift is absent
    - [ ] No bubble map, no wallet, no signature, no transaction
22. Compare with [`crew/examples/field-sheet-example.md`](../crew/examples/field-sheet-example.md).

## Troubleshooting
- **A specialist says "already posted":** it is replying from memory of a different mint. Re-post the Assay. The prompts tell agents to ignore this for a new mint.
- **Crucible waits for notes:** re-paste `crucible.md`. Step 3 says *do NOT wait*.
- **A grade appears without a rating:** that breaks the rules. Grades only come from `rating.band`.
