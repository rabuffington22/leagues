# The Frozen Tundra — Long-Term Plan

## Phase 1: 2026 Rookie Draft (ACTIVE — 2026-04-27)
Draft is live. 12-team, 4-round, linear format, SuperFlex PPR.

### Ryan's picks
| Pick | Overall | Status |
|------|---------|--------|
| 1.02 | 2  | — |
| 1.12 | 12 | — |
| 2.02 | 14 | — |
| 2.11 | 23 | — |
| 3.02 | 26 | — |
| 3.06 | 30 | — |
| 3.09 | 33 | — |
| 4.02 | 38 | — |

### Immediate priorities
- [x] Build draft-tracker.html with SF-adjusted consensus rankings baked in
- [ ] Use draft-tracker.html during live draft — server ready on port 8766
- [ ] Record all picks (Mine / Gone) in real time
- [ ] Update this file with final roster after draft completes

### Draft tracker
- Run: `python3 -m http.server 8766` from `frozen-tundra/` directory
- Open: `http://localhost:8766/draft-tracker.html`
- State saves to localStorage (key: `ftz_v1`)

## Phase 2: Post-Draft
- [ ] Roster strength assessment vs field
- [ ] Identify 2027 rookie draft targets
- [ ] In-season waiver / trade strategy
