# Session Log

## 2026-04-26 — No Flex Zone startup auction

### What we did
- Identified the No Flex Zone league via Chrome (redirected from sleeper.com/leagues)
- Discovered Ryan's actual Sleeper user ID (160225092348297216 / alpacalypse) — the `rbuffington` account exists but has no leagues
- Pulled league settings via Sleeper API: 14-team dynasty auction, $1000 budget, 30 rounds, 2QB/3RB/4WR/2TE, no flex
- Calculated full scoring analysis vs standard/PPR formats
- Pulled 2023, 2024, 2025 season stats from Sleeper and scored them using No Flex Zone rules
- Built 3-year PPG rankings for all four positions
- Iterated through auction budget 4-5 times based on Ryan's feedback and the data

### Key decisions
- **Priority order flipped to TE > QB > WR > RB** after data showed McBride (25.4 PPG) and Bowers (22.5 PPG) score at elite QB levels
- **Herbert removed from QB targets** — only 18.5 PPG across 46 games, sack penalty (-2.5) hurts him consistently
- **Burrow removed from QB targets** — only 35 games in 3 seasons, injury risk too high at QB price points
- **Bo Nix added as primary QB2 target** — 22.6 PPG, played all 34 games across 2 seasons, most durable mid-tier QB
- **McBride ceiling $250, Bowers ceiling $200** — walk away above these

### Draft results so far (auction live as of session end)
- Drake Maye (QB, NE) — WON at $220. Remaining budget: $780.

### Final confirmed budget (remaining $780)
- TE: $300 (McBride ~$240 + Bowers ~$190, or McBride + cheap TE2)
- QB2: $65
- WR: $155 (4 starters, spread thin — acceptable in stars-and-scrubs dynasty)
- RB: $80 (3 starters minimum viable)
- Bench: $50

### Market calibration from draft
- Maye (top-3 dynasty asset) went for $220 — confirms aggressive QB market
- Implies Lamar/Allen tier: $300-370+; Mahomes/Nix tier: $160-200

### Repo created
- github.com/rabuffington22/leagues
- Local: ~/Documents/GitHub/leagues/
- No Flex Zone is the first league added

## 2026-04-26 — Session 2: Tracker sync + roster builder + Apple design

### What we did
- Pulled live Sleeper draft picks via API — 9 picks made, Ryan has Drake Maye ($220), 8 others off the board
- Fixed two bugs in the tracker: Maye appearing as both QB1 and QB2 (tab key was 'qb' instead of 'qb1'), and tab order/labels (was TE/QB2/WR/RB, now QB/WR/TE/RB)
- Rebuilt the Roster tab entirely: side-by-side position columns (QB×4, WR×10, TE×6, RB×6), editable per-slot budgets, live pool display
- Fixed pool not updating in header when slot budget is edited (renderRoster() wasn't being called from updateSlotBudget)
- Full Apple design system refresh: SF Pro font, true black base + dark navy (#0d1421) cards, deep navy frosted glass header (rgba(6,12,24,0.92) + backdrop-filter blur), Apple accent colors, 12–14px border radius, antialiased text

### Key decisions
- **Roster planning slots**: 4 QB, 10 WR, 6 TE, 6 RB — oversized intentionally, will cut at end of draft
- **Pool mechanic**: pool = remaining budget minus sum of all open slot budgets. Lives in header meta line. Updates live on slot budget edit.
- **QB1 tab key**: `'qb1'` not `'qb'` — prevents Maye from being picked up by the QB2 search in renderBudgetBreakdown
- **Design**: Apple dark palette chosen over previous blue-tinted custom palette. Navy cards (#0d1421) over neutral dark gray.

### Market intelligence (as of session end)
- RB elite tier (Bijan $223, Achane $165, Love $175) went 2–4× above tracker ceilings — $80 RB budget will be painful
- WR elite tier (Chase $238, Nabers $190) also running hot — $155 for 4 starters is tight
- QB market: Daniels $220 = same as Maye — mid-tier QBs are expensive. Bo Nix $65 ceiling may be tight.
- **McBride and Bowers both still available** — TE-first strategy remains intact

### Deferred
- No long term plan.md created yet — created this session (see below)

## 2026-04-27 — Session 3: League tab + pick attribution

### What we did
- Added a **League tab** to the auction tracker showing all 14 teams as cards
- Each team card shows starter slots (QB1/2, WR1–4, TE1/2, RB1–3) + bench, player name + price per slot, budget remaining (~$1000 - attributed spend)
- Updated the **Lost button flow**: clicking Lost now shows an inline attribution form (team name + price) with Save/Skip, so other teams' picks can be attributed on the fly
- Already-lost picks show team + price inline; "edit" button to reassign
- Added **Unattributed section** at top of League tab for quick batch-attribution of picks with unknown teams
- Pulled real draft data from Sleeper API (`/draft/{id}/picks` + `/league/{id}/users` + rosters) to identify the actual teams behind the 9 known picks
- Seeded SEED.lost with full `{ team, price }` objects for all 9 known picks
- Fixed loadState merge bug: was overwriting all lost entries to `true` on every load; now non-destructive — preserves attributions, upgrades bare entries when SEED has team info

### Key decisions
- **No toggle/filter** on League tab — just show all teams, simpler
- **No position section headers** in team cards — slot labels (QB1, QB2 etc.) carry enough context via color
- **Teams seeded from API**: AmadorFSU (Josh Allen, Bijan, Achane, J.Mason), coleh44 (Jayden Daniels), revskip (J. Love), kolt78 (Ja'Marr Chase), Chauncey (Malik Nabers)
- SEED.teams pre-populated with these 5 names for autocomplete on future picks

### Deferred
- Auto-sync picks from Sleeper API (would eliminate manual attribution entirely)
