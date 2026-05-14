# Auracle Open Source — landing site

Static, single-file landing page for the open-source / research-only
distribution of Auracle. Deployed separately from the main marketing
site so the messaging is cleanly scoped to the Polar-safe surface:
self-hosted research toolkit, backtesting + simulation, no live trading
or broker connectivity.

## Files

```
auracle-oss/
├── index.html       # The whole landing page — single self-contained file
├── vercel.json      # cleanUrls + security headers
├── assets/
│   └── auracle-mark.svg
└── README.md
```

## Run locally

```bash
cd auracle-oss
python3 -m http.server 8000
open http://localhost:8000/
```

## Deploy to Vercel

Two options, depending on how you want this to relate to the main site:

### Option A — separate Vercel project, subdomain of auracle.dev (recommended)

```bash
cd auracle-oss
vercel               # first run: link / create project (e.g. `auracle-oss`)
vercel --prod        # ship to production
# In Vercel dashboard: add custom domain → opensource.auracle.dev
# Point that DNS at Vercel per the dashboard instructions.
```

Same brand, separate compliance surface, clean URL.

### Option B — completely separate domain

Same as above but in Vercel set the custom domain to a fresh second-level
domain (e.g. `auracle-research.com`). Use this if you want zero brand
overlap with the commercial site for review purposes.

### Option C — separate project on the same repo

Move this directory under a new git repo. Same Vercel project setup as
Option A. Keeps git history clean and stops accidental copy drift with
the main marketing repo.

## Updating

The compliance scope statement is in `index.html` under the `<section class="compliance">`
block. Any time the wording near "Auracle Open Source is" / "is not" / "does not"
changes, update the corresponding Polar product description in the
`docs/polar-descriptions.md` if you keep one — wording must match across both.
