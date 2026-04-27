# No Flex Zone — League Context

## Identity
- Sleeper league ID: `1312167756132536320`
- Sleeper draft ID: `1312167756782645248`
- Season: 2026 | Type: Dynasty startup auction | Teams: 14 | Budget: $1,000

## Roster
2 QB, 3 RB, 4 WR, 2 TE — **no flex spots**. Rigid positional requirements every week.

## Scoring highlights (vs standard)
- Pass TD: **6 pts** (not 4)
- Pass INT: -3, pass INT TD: -4, pass sack: **-2.5** (unusual — penalizes sack-prone QBs)
- Rush TD: **5 pts** (not 6) — slight RB nerf
- Reception: **1.0 PPR** (full)
- TE bonus: **+0.9/rec** → 1.9 effective PPR
- WR bonus: **+0.25/rec** → 1.25 effective PPR
- First down bonuses: rush +0.4, rec +0.5, pass +0.5
- Big play bonuses: 20-29yd rec +0.5, 30-39yd +0.5, 40+yd +1.0
- 20+ carry bonus: +1 pt flat for RBs with 20+ rush attempts in a week

## Draft status (as of 2026-04-26)
Auction is live. 9 picks made so far — market running hot.

### Off the board
| Player | Pos | $ | Winner |
|---|---|---|---|
| Drake Maye | QB | $220 | **RYAN** |
| Josh Allen | QB | $251 | Other |
| Jayden Daniels | QB | $220 | Other |
| Bijan Robinson | RB | $223 | Other |
| De'Von Achane | RB | $165 | Other |
| Jeremiyah Love | RB | $175 | Other |
| Jordan Mason | RB | $25 | Other |
| Ja'Marr Chase | WR | $238 | Other |
| Malik Nabers | WR | $190 | Other |

### Market calibration
RB and WR market is running 2–4× above pre-draft ceilings. TE market not yet tested — McBride and Bowers still available.

## Auction tracker
Single-file tool: `no-flex-zone/auction-tracker.html`
- Serve: `python3 -m http.server 8765` from `no-flex-zone/` directory
- Open: `http://localhost:8765/auction-tracker.html`
- State persists in localStorage (key: `nfz_v4`)
- Tracks: won/lost/hidden players, remaining budget, per-position spend, max safe bid, per-slot budget planning with live pool

### Tracker architecture notes
- Player picks stored as `S.picks[id] = { name, pos, tab, price }` — `pos` is uppercase (QB/WR/TE/RB), `tab` is lowercase position key except QB1 which uses `'qb1'` to avoid being matched as QB2
- Slot budgets stored in `S.slotBudgets` (26 keys: qb1–4, wr1–10, te1–6, rb1–6); defaults in `DEFAULT_SLOT_BUDGETS` constant
- Pool = remaining budget minus sum of open slot budgets; displayed in section-meta header
- SEED includes all known off-the-board players as `lost`; `loadState()` merges new lost players on every load without wiping existing state

## Confirmed spend
| Player | Pos | Price |
|---|---|---|
| Drake Maye | QB | $220 |

Remaining: $780

## Budget (remaining)
| Position | Budget | Notes |
|---|---|---|
| TE | $450 | Targeting **both** McBride ($250 ceil) + Bowers ($200 ceil) |
| QB2 | $65 | Bo Nix preferred |
| WR | $155 | 4 starters, stars-and-scrubs |
| RB | $80 | 3 starters minimum |
| Bench | $30 | Mostly $1 bids |

## Priority order
TE first — go for **both** McBride AND Bowers → QB2 → WR → RB last

## Target ceilings
- **Trey McBride** (TE, ARI): $250 — best PPG player in dataset (22.4 avg, 50/51 games)
- **Brock Bowers** (TE, LV): $200 — elite PPG but injury risk (29 games in 2 years)
- **QB2**: $65 max — Bo Nix preferred (22.6 PPG, 34/34 games)

## Players removed from target list
- Justin Herbert — 18.5 PPG 3-yr avg, sack penalty consistently hurts him
- Joe Burrow — only 35 games in 3 seasons, injury risk too high
