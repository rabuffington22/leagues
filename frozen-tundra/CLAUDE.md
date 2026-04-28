# The Frozen Tundra — League Context

## Identity
- Sleeper league ID: `1312105540691722240`
- Sleeper draft ID: `1312105540708474880`
- Season: 2026 | Type: Dynasty rookie draft | Teams: 12 | Rounds: 4 | Format: Linear (same order every round)

## Roster
1 QB, 2 RB, 3 WR, 1 TE, 1 SuperFlex, 3 Flex — 29 bench slots

## Scoring highlights
- Pass TD: **4 pts** (standard)
- Reception: **1.0 PPR** (full)
- SuperFlex — QBs valuable, ranked higher than non-SF consensus

## Ryan's 2026 Draft Picks
| Pick | Overall | Player | Status |
|------|---------|--------|--------|
| 1.02 | 2  | Fernando Mendoza (QB, LVR) | ✓ Drafted |
| 1.12 | 12 | — | Pending |
| 2.02 | 14 | — | Pending |
| 2.11 | 23 | — | Pending |
| 3.02 | 26 | — | Pending |
| 3.06 | 30 | — | Pending |
| 3.09 | 33 | — | Pending |
| 4.02 | 38 | — | Pending |

## Draft slot order (linear, repeats each round)
| Slot | Team | Roster |
|------|------|--------|
| 1 | fe_b | 7 |
| 2 | Old ass Play-Doh (Ryan) | 10 |
| 3 | The Flock (GieseDynasty) | 5 |
| 4 | Bump and Run (RieSim) | 1 |
| 5 | DAKstreet Boys (jrray) | 11 |
| 6 | lordsimkins | 2 |
| 7 | No Really, We Suck (kalhuillier9) | 6 |
| 8 | Hawk Tua (mverstra) | 8 |
| 9 | Belichick Film School (seigo24) | 9 |
| 10 | Ra Doggin in the LaPorta (nfolse) | 12 |
| 11 | Innis To Win This (Innis) | 4 |
| 12 | prestond | 3 |

## Draft tracker
Single-file tool: `frozen-tundra/draft-tracker.html`
- Serve: `python3 -m http.server 8766` from `frozen-tundra/` directory
- Open: `http://localhost:8766/draft-tracker.html`
- State persists in localStorage (key: `ftz_v1`)

### Tracker architecture notes
- `S.cur` = current overall pick number (1–48)
- `S.picks[id] = { name, pos, nfl, pickNum }` — Ryan's drafted players
- `S.gone[id] = { name, pickNum }` — players taken by other teams
- RYAN_PICKS = Set([2, 12, 14, 23, 26, 30, 33, 38])
- Rankings are SuperFlex-adjusted (Mendoza #3, Ty Simpson #9, Nussmeier #23)

## Consensus Rankings (SuperFlex-adjusted, as of 2026-04-27)
Sources: FantasyPros post-NFL-draft + KTC blended

| # | Player | Pos | NFL |
|---|--------|-----|-----|
| 1 | Jeremiyah Love | RB | ARI |
| 2 | Carnell Tate | WR | TEN |
| 3 | Fernando Mendoza | QB | LVR |
| 4 | Jordyn Tyson | WR | NOR |
| 5 | Makai Lemon | WR | PHI |
| 6 | KC Concepcion | WR | CLE |
| 7 | Jadarian Price | RB | SEA |
| 8 | Kenyon Sadiq | TE | NYJ |
| 9 | Ty Simpson | QB | LAR |
| 10 | Omar Cooper Jr. | WR | NYJ |
| 11 | Denzel Boston | WR | CLE |
| 12 | Eli Stowers | TE | PHI |
| 13 | Jonah Coleman | RB | DEN |
| 14 | Nicholas Singleton | RB | TEN |
| 15 | Chris Bell | WR | MIA |
| 16 | Germie Bernard | WR | PIT |
| 17 | Chris Brazzell II | WR | CAR |
| 18 | Elijah Sarratt | WR | BAL |
| 19 | Mike Washington Jr. | RB | LVR |
| 20 | Emmett Johnson | RB | KCC |
