# No Flex Zone — Session Log

## 2026-04-26 — Session 1 (Startup)
- Auction is live today. Ryan is slot 13/14, $1,000 budget.
- Only confirmed pick: Drake Maye at $220. Remaining: $780.
- 3-year PPG rankings built and committed (2023–2025 Sleeper data, NFZ scoring applied).
- Priority strategy: TE first — targeting **both** McBride AND Bowers → QB2 → WR → RB last.
- TE budget raised to $450 (McBride ceil $250 + Bowers ceil $200). Going for both.
- McBride: 22.4 PPG, 50/51 games, ascending. #1 dynasty target overall.
- Bowers: 22.5 PPG, 29 games — walk above $200, but worth pursuing.
- QB2 ceiling $65: Bo Nix preferred (34/34 games, 22.6 PPG).
- WR budget $155 (stars-and-scrubs), RB budget $80, Bench $30 (mostly $1 bids).
- Built live auction tracker (auction-tracker.html) — served at localhost:8765.
- Herbert and Burrow explicitly removed from targets.

## 2026-04-26 — Session 2 (Tracker build + draft start)
- Auction went live during this session. Josh Allen nominated first — bid up to $251, won by AmadorFSU.
- Bijan Robinson nominated second by tking.
- Tracker built and heavily iterated: budget breakdown by position, per-player ceilings, won/lost/hide states, PPG-sorted lists, starter/bench divider, real header.
- Player lists expanded to ~20 per position, sorted by PPG. Players with estimated PPG noted.
- Hide/unhide added — hides player from list without marking them as gone from draft.
- Starter count separator: TE after #2, QB after #2, WR after #4, RB after #3.
- QB budget card redesigned: shows QB1 (Maye $220) and QB2 slot inline rather than two separate boxes.
- TE strategy confirmed: going for BOTH McBride ($250 ceil) and Bowers ($200 ceil) — TE budget $450.
- QB2 ceiling reduced from $80 to $65 to accommodate dual-TE spend.
- Server: `python3 -m http.server 8765` from no-flex-zone/ — runs in background.
- localStorage key is `nfz_v4` (bumped due to state schema changes this session).
- User noted tracker should be a reusable template for future leagues (auction and snake).
