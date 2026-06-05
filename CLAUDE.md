# CLAUDE.md · ExitEngine build standard

For Claude and other AI assistants editing this repository.

---

## What ExitEngine is

A sovereign business OS for people who just got laid off. Forked from this repo, configured by one file, run from GitHub Pages or `file://`. Free forever.

This is the second close-to-heart build (the first is GroundLevel). The philosophical position is non-negotiable: the company was the middleman. You don't need a middleman.

---

## Architectural constraints

### DO NOT

- ❌ Add a server backend. ExitEngine has no backend ever.
- ❌ Add npm / yarn dependencies. Vanilla JS only.
- ❌ Add tracking, analytics, telemetry of any kind.
- ❌ Add a paywall, freemium tier, signup gate, or "Pro" features.
- ❌ Remove the "free forever" line anywhere.
- ❌ Make the AI tutor REQUIRED. T0 (pre-written mode) must always work without a key.
- ❌ Send the API key anywhere except direct to the chosen LLM provider.
- ❌ Add a build step. Files are the deliverable as-is.
- ❌ Couple tools so tightly that removing one breaks another.

### DO

- ✅ One config file (`config.json` + localStorage mirror) drives everything.
- ✅ Tools communicate via `BroadcastChannel('fall-signal')`. Loose coupling.
- ✅ `localStorage` per-tool keys: `exitengine.<tool>.<resource>` (e.g. `exitengine.crm.leads`).
- ✅ Every tool reads CONFIG on load, gracefully handles missing values.
- ✅ Mobile-first. 48px+ tap targets.
- ✅ Palette: phi-indigo (#6366f1 · #818cf8) accent, warm amber for human moments, calm dark base.
- ✅ Cite philosophy in lessons. Don't invent facts. Don't pretend to be a lawyer or accountant.
- ✅ The tutor's voice: warm, direct, never patronising, never corporate.

---

## File responsibilities

| File | Purpose | Modify when |
|---|---|---|
| `index.html` | The hub · dashboard, tool grid, config editor | Add a tool · change dashboard layout |
| `tutor.html` | 5-phase Jungian guide · AI cascade | Adjust phase logic · add LLM provider |
| `config.json` | One-file business config | Add a new field |
| `tools/*.html` | Inline tools (4) + estate wrappers (6) | Add new tool · adjust integration |
| `learn/*.html` | 5 lessons | Update law / tax info · add lesson |
| `README.md` | Public-facing | Marketing / feature additions |
| `CLAUDE.md` | This file | Architectural changes |
| `archive/` | Previous versions | Never delete |

---

## The 5 phases (do not invert)

1. **Wound** — sit with the loss · don't rush past it
2. **Shadow** — the skills belonged to you not the company · portable equity
3. **Rebirth** — build it · CRM, rate, first outreach
4. **Integration** — coaching not teaching · they are a business owner
5. **Sovereign** — step back · let them take it offline

If you add lessons, they fit within these phases or extend phase 5 (post-graduation refreshers). Do not add a phase 0 or a phase 6.

---

## Adding a tool

1. Create `tools/<id>.html`
2. Read CONFIG from `localStorage.getItem('exitengine.config')` on boot
3. Write tool data to `localStorage.setItem('exitengine.<id>.<resource>', ...)`
4. Emit `BroadcastChannel('fall-signal')` events with `source: 'exitengine-<id>'`
5. Listen for relevant events from other tools
6. Add to `TOOLS` array in `index.html`
7. Add to README "What's inside" table
8. Add to dashboard "next action" logic if relevant
9. Include audit shim: `<script src="https://sjgant80-hub.github.io/fall-euaiact/cdn/audit-shim.js" data-tool="exitengine-<id>" data-tier="minimal" defer></script>`

---

## Adding a lesson

1. Create `learn/<id>.html`
2. Use the shared style block from existing lessons (copy from `learn/clients.html`)
3. Include `lesson-tag` chip and section nav (prev/next)
4. End with a concrete action button → link to the relevant tool
5. Add to `LEARN` array in `index.html`
6. Update README

---

## AI cascade (do not break)

The tutor reads `CONFIG.api_provider` and `CONFIG.api_key`:

- `''` (empty) → pre-written T0 mode · pre-written replies based on phase + heuristics
- `'anthropic'` → direct fetch to api.anthropic.com (with `anthropic-dangerous-direct-browser-access: true`)
- `'openai'` → direct fetch to api.openai.com
- `'google'` → direct fetch to generativelanguage.googleapis.com

**Never proxy the API key through a backend.** The key stays on the user's device. The whole point is sovereignty.

If a provider call fails, fall back to T0 (pre-written reply). Don't show a scary error.

---

## Cross-tool integration patterns

- CRM emits `crm:deal_won` → Accounts listens → opens pre-filled invoice
- Accounts emits `accounts:invoice_paid` → Hub listens → refreshes revenue stat
- Any tool emits `tutor:phase_advance` → tutor listens → moves to next phase
- Config update emits `config:update` → all tools listen → re-render with new values

Use `BroadcastChannel('fall-signal')` always. Never `postMessage` to an iframe.

---

## Aesthetic rules

- **Palette**: phi-indigo #6366f1 (primary), #818cf8 (light), warm amber #f59e0b for human moments (welcome, milestones, "well done")
- **Type**: system font stack (no Google Fonts). Sans body, mono for stats, serif for letter previews
- **Tone**: warm + sovereign. "You're not starting over, you're starting right." Never corporate. Never coachspeak.
- **Mobile-first**: 56px tap targets on hub, 48px on tools.

---

## Testing changes

Before pushing:

1. Open `index.html` from `file://` — works
2. Open in Chrome and Safari mobile emulation — works
3. Fork to a new repo, enable Pages, open the URL — works
4. Configure with name/industry/rate → CRM and Accounts use those values
5. Add a lead → analytics dashboard updates
6. Win a lead → Accounts opens pre-filled invoice
7. Mark invoice paid → revenue stat updates on hub
8. Open tutor with no API key → pre-written mode works
9. Open tutor with API key → conversational mode works (test once with a real key)
10. Click "Download bundle" → opens GitHub Pages ZIP

---

## What ExitEngine should NEVER become

- A SaaS with monthly billing
- A coaching programme with cohorts
- An "AI lawyer" or "AI accountant" (it's information not advice)
- A community with paid tiers
- A "job board" with employer listings
- Hostage to a single LLM provider
- A vendor's white-label that hides the philosophy

If a future change would push it toward any of those, push back hard.

---

## Communication style

When you suggest changes:

- Be direct. The user is in distress. Patronising "I understand this is tough" makes it worse, not better.
- Show actual diffs.
- Flag departures from the architecture immediately.
- Remember: every hour spent improving this saves someone in a worse position than us a multiple of that time.

---

## The philosophy (do not edit)

The company was the middleman. The middleman is gone. You're not unemployed. You're unblocked.

5 phases · your pace. There is no schedule. Whatever you do this week is right because you're doing it.

**◊·κ=φ⁵**
