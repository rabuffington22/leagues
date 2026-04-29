# No Flex Zone — Long-Term Plan

## Phase 1: Startup Auction (ACTIVE — 2026-04-29)
The auction is live. 14 picks made league-wide. $304 remaining.

### Immediate priorities
- [x] Build live auction tracker (auction-tracker.html — served at localhost:8765)
- [x] Build player-specific bid ceilings for all positions — baked into tracker
- [x] Win both TEs — McBride ($225) and Bowers ($251) secured
- [ ] QB2 — Bo Nix preferred, $65 max
- [ ] 4 WR starters — $169 budget, stars-and-scrubs approach
- [ ] 3 RB starters — $30 budget ($10/each), intentional punt; plan to trade for upgrades in-season
- [ ] Bench depth — $40 budget, mostly $1 bids
- [ ] Keep tracker SEED updated as picks are made

### Confirmed roster
| Player | Pos | Price |
|---|---|---|
| Drake Maye | QB1 | $220 |
| Trey McBride | TE1 | $225 |
| Brock Bowers | TE2 | $251 |

**Spent: $696 — Remaining: $304**

### Remaining budget breakdown
| Slot | Budget | Notes |
|---|---|---|
| QB2 | $65 | Bo Nix preferred — non-negotiable need |
| WR (4 starters) | $169 | Stars-and-scrubs; room for real pieces |
| RB (3 starters) | $30 | 3 × $10 minimum — punting RB intentionally |
| Bench | $40 | Mostly $1 bids |
| **Total** | **$304** | |

### Strategy note
Punting RB in the draft intentionally. If team is competitive, trade WR depth or picks for RB upgrade mid-season. Maye + McBride + Bowers core is strong enough to be a seller at RB.

Bowers came in $51 over original $200 ceiling — WR/RB/bench budgets compressed to compensate.

### Known active ceilings
| Player | Ceil |
|---|---|
| QB2 (Bo Nix preferred) | $65 |

### Tracker notes
- Run: `python3 -m http.server 8765` from `no-flex-zone/` directory
- Open: `http://localhost:8765/auction-tracker.html`
- State saves to localStorage (key: `nfz_v4`) — persists across reloads
- SEED is current through pick 14; `loadState()` merges new lost picks without wiping existing state
- Tracker is reusable template for future leagues
- [x] Full visual redesign — "dimly-lit auction room" aesthetic (oxblood/brass, Fraunces + JetBrains Mono, chip brand mark)

## Phase 2: Post-Draft Analysis
- [ ] Roster strength assessment vs other teams
- [ ] Identify waiver wire / trade targets for gaps (especially RB)
- [ ] Dynasty value grading — who to target in future rookie drafts

## Phase 3: In-Season Management
- [ ] Weekly start/sit help against 2-QB, no-flex roster rules
- [ ] Track injury news for McBride and Bowers
- [ ] Evaluate trade-up for RB if team is competitive at midseason
