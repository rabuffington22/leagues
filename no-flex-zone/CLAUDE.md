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

## Draft status (as of 2026-04-28)
Auction is live. 14 picks made so far — market running very hot.

### Off the board
| Player | Pos | $ | Winner |
|---|---|---|---|
| Drake Maye | QB | $220 | **RYAN** |
| Trey McBride | TE | $225 | **RYAN** |
| Brock Bowers | TE | $251 | **RYAN** |
| Josh Allen | QB | $251 | AmadorFSU |
| Jayden Daniels | QB | $220 | coleh44 |
| Bijan Robinson | RB | $223 | AmadorFSU |
| De'Von Achane | RB | $165 | AmadorFSU |
| Jeremiyah Love | RB | $175 | revskip |
| Jordan Mason | RB | $25 | AmadorFSU |
| Ja'Marr Chase | WR | $238 | kolt78 |
| Malik Nabers | WR | $190 | Chauncey |
| Jaxon Smith-Njigba | WR | $231 | SunnyBrown |
| Jahmyr Gibbs | RB | $241 | kolt78 |
| Puka Nacua | WR | $225 | TimboDAsavage |

### Market calibration
WR and RB market running 2–4× above pre-draft ceilings. TE market was fair (McBride $225, Bowers $251). New teams: SunnyBrown, TimboDAsavage confirmed active.

## Auction tracker
Single-file tool: `no-flex-zone/auction-tracker.html`
- Serve: `python3 -m http.server 8765` from `no-flex-zone/` directory
- Open: `http://localhost:8765/auction-tracker.html`
- State persists in localStorage (key: `nfz_v4`)
- Tracks: won/lost/hidden players, remaining budget, per-position spend, max safe bid, per-slot budget planning with live pool

### Tracker architecture notes
- Player picks stored as `S.picks[id] = { name, pos, tab, price }` — `pos` is uppercase (QB/WR/TE/RB), `tab` is lowercase position key except QB1 which uses `'qb1'` to avoid being matched as QB2
- Slot budgets stored in `S.slotBudgets` (30 keys: qb1–4, wr1–13, te1–7, rb1–6); defaults in `DEFAULT_SLOT_BUDGETS` constant
- Pool = remaining budget minus sum of open slot budgets; displayed in section-meta header
- SEED includes all known off-the-board players as `lost`; `loadState()` merges new lost players on every load without wiping existing state
- Lost picks stored as `S.lost[id] = { team, price }` (attributed) or `true` (unattributed); merge logic upgrades unattributed entries when SEED has team info
- `S.teams` = array of known team names, used for autocomplete when attributing picks
- League tab shows all team cards (Ryan first, others by spend); Unattributed section for picks with no team assigned yet
- Sleeper usernames for known teams: AmadorFSU, coleh44, revskip, kolt78, Chauncey, SunnyBrown, TimboDAsavage
- Each player in TARGETS has `y25: { pts, g }` for 2025 season totals (derived from trend data in notes; estimated where not available). Player tabs sort by `y25.pts` descending. Stats columns show 2025 data; 3yr context shown as note line under player name.

### Tracker design system (as of 2026-04-28)
- Aesthetic: "dimly-lit auction room" — true black, no rounded cards, sharp architectural feel
- Colors: oxblood (`#b3463f`) is dominant accent; brass (`#c9a14b`) for luxury moments (title, Won buttons); sage green (`#7fbf6e`) for won state only. All positions share oxblood — no QB-blue/WR-green color coding.
- Fonts: Fraunces (serif, headings + brand title), JetBrains Mono (labels, stat numbers, buttons), Inter (body) — all from Google Fonts
- **No italics anywhere** — `font-style: normal` on all elements including `.ital` spans and `.roster-section-pos`
- **Section titles all oxblood** — `.section-title { color: var(--bad-2) }`, `.ital` spans inherit; no white/oxblood split
- Do not use `border-radius > 6px`, drop shadows larger than 1–2px, or position-specific colors when modifying this file

## Confirmed spend
| Player | Pos | Price |
|---|---|---|
| Drake Maye | QB | $220 |
| Trey McBride | TE | $225 |
| Brock Bowers | TE | $251 |

Remaining: $304

**Note:** Bowers came in $51 over the $200 ceiling. WR/RB/bench budgets need to compress — see breakdown below.

## Budget (remaining)
| Position | Budget | Notes |
|---|---|---|
| QB2 | $65 | Bo Nix preferred — non-negotiable need |
| WR | $169 | 4 starters — more room to get real pieces |
| RB | $30 | 3 × $10 minimum bids — plan to trade for RBs in-season |
| Bench | $40 | Mostly $1 bids |
| **Total** | **$304** | |

## Priority order
QB2 → WR → RB ($10 bids, don't overpay)

## Strategy note
Punting RB in the draft intentionally. If team is competitive, trade WR depth or picks for RB upgrade mid-season. Maye + McBride + Bowers core is strong enough to be a seller at RB.

## Target ceilings
- **QB2**: $65 max — Bo Nix preferred (22.6 PPG, 34/34 games)

## Players removed from target list
- Justin Herbert — 18.5 PPG 3-yr avg, sack penalty consistently hurts him
- Joe Burrow — only 35 games in 3 seasons, injury risk too high
