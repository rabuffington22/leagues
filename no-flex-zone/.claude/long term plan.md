# No Flex Zone — Long-Term Plan

## Phase 1: Startup Auction (ACTIVE — 2026-04-26)
The auction is live. Nomination slot 13 of 14. $1,000 budget.

### Immediate priorities
- [x] Build live auction tracker (auction-tracker.html — served at localhost:8765)
- [x] Build player-specific bid ceilings for all positions — baked into tracker
- [ ] Complete roster: need QB2, 2 TEs, 4 WR starters, 3 RB starters, bench depth
- [ ] Keep tracker updated as picks are made during draft

### Confirmed roster
| Player | Pos | Price |
|---|---|---|
| Drake Maye | QB | $220 |

### Known ceilings
| Player | Ceil |
|---|---|
| Trey McBride (TE) | $250 |
| Brock Bowers (TE) | $200 |
| QB2 (Bo Nix preferred) | $65 |

### Tracker notes
- Run: `python3 -m http.server 8765` from `no-flex-zone/` directory
- Open: `http://localhost:8765/auction-tracker.html`
- State saves to localStorage (key: `nfz_v4`) — persists across reloads
- Tracker is reusable template for future leagues

## Phase 2: Post-Draft Analysis
- [ ] Roster strength assessment vs other teams
- [ ] Identify waiver wire / trade targets for gaps
- [ ] Dynasty value grading — who to target in future rookie drafts

## Phase 3: In-Season Management
- [ ] Weekly start/sit help against 2-QB, no-flex roster rules
- [ ] Track injury news for McBride (if won) / Bowers (if won)
