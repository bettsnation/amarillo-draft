# amarillo-draft

Standalone draft-day dashboard for the FantasyBetts league — served at
**https://amarillo.fantasybetts.com** via GitHub Pages.

One self-contained `index.html`, no dependencies, no backend. NBA-style
draft-position selection: the card at the top shows who's on the clock (the
official selection order Rod set on 2026-08-20), tapping an open pick assigns
it, and the clock advances. Paid pills track 2026 dues ($150). State persists
in localStorage on the viewer's device — this is a one-screen-at-the-draft
tool, not a multi-user live board.

Seeded once from fantasybetts prod (owners, 2025 teams/placements). To change
the roster or seed order, edit `SEED` in `index.html` and push — Pages
redeploys on push to `main`.

Known assumption: "Berg" = Jason Barenberg, "Dad Berg" = Jeff Barenberg. If
backwards, either swap the two rows' arrows in the UI or fix the SEED.
