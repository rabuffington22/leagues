# The Frozen Tundra — Long-Term Plan

## Phase 1: 2026 Rookie Draft (ACTIVE — 2026-04-29)
Draft is live. 12-team, 4-round, linear format, SuperFlex PPR. Through pick 26 (round 3.02).

### Ryan's picks
| Pick | Overall | Player | Status |
|------|---------|--------|--------|
| 1.02 | 2  | Fernando Mendoza (QB, LVR) | ✓ |
| 1.10 | 10 | Omar Cooper Jr. (WR, NYJ)  | ✓ |
| 1.12 | 12 | Ty Simpson (QB, LAR)       | ✓ |
| 2.02 | 14 | Germie Bernard (WR, PIT)   | ✓ |
| 2.11 | 23 | Zachariah Branch (WR, ATL) | ✓ |
| 2.12 | 24 | Chris Brazzell II (WR, CAR)| ✓ |
| 3.02 | 26 | Ja'Kobi Lane (WR, BAL)     | ✓ |
| 3.09 | 33 | — | Pending |
| 4.02 | 38 | — | Pending |

### Immediate priorities
- [x] Build draft-tracker.html with SF-adjusted consensus rankings baked in
- [x] Use draft-tracker.html during live draft — server ready on port 8766
- [x] Record all picks (Mine / Gone) in real time — 7 of 9 picks made
- [ ] Update this file with final roster after draft completes

### Draft tracker
- Run: `python3 -m http.server 8766` from `frozen-tundra/` directory
- Open: `http://localhost:8766/draft-tracker.html`
- State saves to localStorage (key: `ftz_v1`)

## Phase 2: Post-Draft
- [ ] Roster strength assessment vs field
- [ ] Identify 2027 rookie draft targets
- [ ] In-season waiver / trade strategy
