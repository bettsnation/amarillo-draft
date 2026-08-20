# amarillo-draft

Standalone draft-day dashboard for the FantasyBetts league — served at
**https://amarillo.fantasybetts.com** via GitHub Pages.

One self-contained `index.html`, no dependencies, no backend. NBA-style
draft-position selection: the card at the top shows who's on the clock (the
official selection order Rod set on 2026-08-20), tapping an open pick assigns
it, and the clock advances. Paid pills track 2026 dues ($150). No login anywhere.

## How updates flow (the actual workflow)

Members tell Rod their pick in the group chat; Rod tells a Claude Code
session; the session edits `SEED.slots` / `SEED.paid` in `index.html`,
**bumps `SEED.rev`**, and pushes. Pages redeploys in ~30s and every visitor
sees the new board on refresh — the rev bump discards any stale
locally-saved state on visitors' devices.

Local taps on the page (picks, paid pills) still work and persist per-device
between publishes — useful at the draft table — but the published file is the
source of truth: export the state and hand it to the session if local edits
need to become official.

Seeded from fantasybetts prod (owners, 2025 teams/placements).

Known assumption: "Berg" = Jason Barenberg, "Dad Berg" = Jeff Barenberg. If
backwards, either swap the two rows' arrows in the UI or fix the SEED.
