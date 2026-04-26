# Leagues — Project Context

One repo, one directory per league. Each league directory has its own CLAUDE.md with league-specific context.

## Repo structure

```
leagues/
├── CLAUDE.md                        # this file — general conventions only
├── README.md                        # league index
├── no-flex-zone/
│   ├── CLAUDE.md                    # league-specific context
│   ├── league.json                  # Sleeper IDs, roster, scoring settings
│   ├── auction-budget.md            # budget, targets, confirmed spend
│   └── player-values-2023-2025.md  # 3-year PPG rankings
└── ...
```

## Sleeper API

All public, no auth required.

| Endpoint | Purpose |
|---|---|
| `GET /user/{username}` | Resolve username → user_id |
| `GET /user/{user_id}/leagues/nfl/{season}` | All leagues for a user |
| `GET /league/{league_id}` | League settings and scoring |
| `GET /draft/{draft_id}` | Draft metadata (type, budget, timer, status) |
| `GET /draft/{draft_id}/picks` | Completed picks |
| `GET /players/nfl` | Full player DB (~14MB, once per session) |
| `GET /stats/nfl/regular/{year}` | Season stats by player ID |

## Ryan's Sleeper identity
- Username: `alpacalypse`
- User ID: `160225092348297216`
- Note: `rbuffington` account exists but has no leagues — use `alpacalypse`

## How PPG rankings are calculated

Pull stats from `/stats/nfl/regular/{year}`, apply the league's `scoring_settings` in Python.
Store player DB in `/tmp/nfz_players.json` — reuse within a session, re-download if stale.

Gotchas:
- `bonus_rec_te` / `bonus_rec_wr` multiply against `rec` count (per-reception position bonus)
- `bonus_rush_att_20` is a flat +1 if season `rush_att >= 20`
- `pass_sack` is negative — already in stats as a positive integer, apply as penalty
- Use 3-year evaluation window, minimum 10 games to qualify, sort by avg PPG
