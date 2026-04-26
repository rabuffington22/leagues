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
