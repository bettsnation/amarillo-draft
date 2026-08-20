# amarillo-draft

Standalone draft-day dashboard for the FantasyBetts league — served at
**https://amarillo.fantasybetts.com** via GitHub Pages.

One self-contained `index.html`, no dependencies, no backend. NBA-style
draft-position selection: the card at the top shows who's on the clock (the
official selection order Rod set on 2026-08-20), tapping an open pick assigns
it, and the clock advances. Paid pills track 2026 dues ($150). No login anywhere. **Read-only since 2026-08-20** — no buttons, no local
state; the published file is the only state. All 14 owners are paid.

## How updates flow (the actual workflow)

Members announce their pick in the group chat; Rod tells a Claude Code
session; the session adds the pick to `SEED.slots` in `index.html`, bumps
`SEED.rev`, and pushes. Pages redeploys in ~30s and every visitor sees the
new board on refresh.

Seeded from fantasybetts prod (owners, 2025 teams/placements).

Known assumption: "Berg" = Jason Barenberg, "Dad Berg" = Jeff Barenberg. If
backwards, either swap the two rows' arrows in the UI or fix the SEED.
