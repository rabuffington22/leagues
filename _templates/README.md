# Draft Tracker Templates

Two working templates live here. Copy one into a new league folder and fill in the
CONFIGURE block — everything else is ready to go.

## Setup: Startup Auction

1. `cp _templates/startup-auction-template.html new-league/auction-tracker.html`
2. Open the file, find the **CONFIGURE** block at the top of `<script>`
3. Set `LEAGUE_ABBR`, `LEAGUE_NAME`, `STORAGE_KEY` (unique!), `TOTAL_BUDGET`, `TOTAL_ROSTER`
4. Set `STARTER_SLOTS`, `ROSTER_SLOTS_CONFIG`, and `DEFAULT_SLOT_BUDGETS` to match your league's roster format
5. Set `DRAFT_ID` (grab from the Sleeper draft URL), and populate `UID_TEAM` as managers nominate
6. Update the **Scoring** card in the HTML header (search `<!-- SCORING CARD -->`)
7. Update the brand subtitle in HTML (search `<!-- BRAND SUB -->`) to match your roster format
8. Serve: `python3 -m http.server 8765` from the league folder
9. Open: `http://localhost:8765/auction-tracker.html`

## Setup: Rookie Linear Draft

1. `cp _templates/rookie-draft-template.html new-league/draft-tracker.html`
2. Open the file, find the **CONFIGURE** block at the top of `<script>`
3. Set `LEAGUE_ABBR`, `LEAGUE_NAME`, `STORAGE_KEY`, `TOTAL`, `TEAMS`, `ROUNDS`
4. Set `MY_ROSTER_ID` (from Sleeper roster API)
5. Set `SLOT_TO_ROSTER` and `ROSTER_NAME` (from Sleeper draft/roster API)
6. Set `DRAFT_ID` (from Sleeper draft URL)
7. Add traded picks to `TRADE_MAP` as they're announced
8. Populate `DYNASTY_ROSTER` if this is a rookie add-on draft (leave `[]` for startup)
9. Serve: `python3 -m http.server 8766` from the league folder
10. Open: `http://localhost:8766/draft-tracker.html`

## Sleeper API cheat sheet

All public, no auth required.

```
# Get Ryan's user_id (don't change this — it's 160225092348297216)
GET https://api.sleeper.app/v1/user/alpacalypse

# Get league info (scoring, roster positions)
GET https://api.sleeper.app/v1/league/{league_id}

# Get roster_id → owner mapping
GET https://api.sleeper.app/v1/league/{league_id}/rosters

# Get team display names
GET https://api.sleeper.app/v1/league/{league_id}/users

# Get draft metadata + slot_to_roster_id
GET https://api.sleeper.app/v1/draft/{draft_id}

# Get completed picks (polled every 3 min by the tracker)
GET https://api.sleeper.app/v1/draft/{draft_id}/picks
```

## localStorage keys

Each tracker uses a unique key so multiple leagues don't share state.
Convention: `{abbr_lowercase}_v1` — bump to `_v2` to wipe stored state.

Examples: `nfz_v1`, `ftz_v1`, `rkl_v1`, `mfl_v1`

## Templates still needed (build when first needed)

- **startup-linear-template.html** — snake/linear format for startup dynasty drafts
- **rookie-auction-template.html** — auction format for rookie-only drafts

Both would be minor variants of the existing templates (linear = no price input;
rookie auction = no veteran player list, simpler budget model).
