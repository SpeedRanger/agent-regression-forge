# Agent Regression Forge

Agent Regression Forge turns a failed AI coding-agent run into deterministic
regression checks, guardrails, and a next prompt.

Live target:

- Site: https://speedranger.github.io/agent-regression-forge/
- Repo: https://github.com/SpeedRanger/agent-regression-forge
- Public request form: https://github.com/SpeedRanger/agent-regression-forge/issues/new?template=regression_pack_request.yml

## Why this exists

AI coding agents are good enough to create dangerous success-shaped work:
changed files, confident summaries, skipped tests, broad fallback logic, and
adjacent behavior drift. The missing layer is not another coding agent. It is a
small proof forge that turns the failure into tests and rules the next run must
obey.

## Public product

- `index.html` - static first-use app
- `.github/ISSUE_TEMPLATE/regression_pack_request.yml` - public-safe paid slot request
- `sample-regression-pack.md` - example output
- `launch-day-buyer-packet.md` - buyer-facing offer and proof boundary
- `reserve-slot.md` - public-safe slot reservation page
- `product-hunt-launch-assets.md` - Product Hunt launch copy
- `product-hunt-submit-handoff-2026-06-08.md` - submit fields and manual blocker
- `launch-status.json` - proof gates
- `launch-ledger.md` - public launch state and revenue slots
- `llms.txt` - machine-readable product summary
- `SECURITY.md` - public safety boundary

## Paid wedge

The first paid unit is a `$19` public/redacted "failure to regression pack"
service.

The buyer sends one public or redacted agent failure and receives:

- likely failure modes
- deterministic regression checks
- test scaffold suggestions
- guardrail rules
- proof checklist
- next prompt

One paid slot clears the `$10` target before fees only when receipt, checkout
export, paid invoice, or equivalent buyer-confirmed payment evidence exists.

## Run locally

Open `index.html` directly or serve the folder:

```powershell
python -m http.server 4193 -d ui/agent-regression-forge
```

Then open `http://localhost:4193`.

## Hard limits

Agent Regression Forge does not guarantee Product Hunt placement, bug fixes,
agent correctness, or revenue. It creates a concrete regression-pack artifact
from public/redacted inputs.
