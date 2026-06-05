# ◊·κ=φ⁵ · ExitEngine

> You just got laid off.
> Here's your company.

Fork this repo. Enable GitHub Pages. Open the URL. Configure once.
You're running a complete independent business in 10 minutes.

**Free forever. Open source. MIT. Sovereign.**

---

## What this is

A single GitHub repository containing every tool a laid-off professional needs to start an independent business — connected, configured by one file, working offline.

10 tools. 5 lessons. 1 tutor. 0 monthly fees.

**The company was the middleman. You don't need a middleman.**

---

## Fork and run · 10 minutes

1. **Fork** this repo to your GitHub account (one click in the top right).
2. **Enable Pages**: Settings → Pages → Source: `Deploy from a branch` → `main` / `(root)`.
3. **Open** `https://<your-username>.github.io/exitengine/`.
4. **Configure**: click the "configure" chip at the top. Enter your name, industry, rate. Optionally paste an API key for the AI tutor.
5. **Start**: open the AI Tutor or read "Just got laid off — now what?".

You're in business.

---

## What's inside

### Hub (`index.html`)
Reads your config. Shows your dashboard. Live pipeline value, this-month revenue, overdue invoices, next action. Tool grid. Lesson grid. Download-bundle button for offline sovereignty.

### Tutor (`tutor.html`)
The soul of ExitEngine. Five-phase Jungian journey:

| Phase | Name | What happens |
|---|---|---|
| 1 | The wound | Acknowledge the loss. Don't rush past it. |
| 2 | The shadow | The skills belonged to you, not the company. Reframe. |
| 3 | The rebirth | Build the company. CRM. Rate. First outreach. |
| 4 | The integration | You're a business owner now, not an ex-employee. Coaching, not teaching. |
| 5 | The sovereign | You don't need the tutor anymore. Take it offline. |

Works in **pre-written mode** (no API key, full T0 experience).
Becomes **conversational** with an Anthropic / OpenAI / Gemini key (BYOK · key stays on your device · direct API calls, no proxy).

### Tools (`tools/`)
| Tool | What | Inline or Estate? |
|---|---|---|
| `crm.html` | Client pipeline, deal tracking | Inline (works offline) |
| `accounts.html` | Invoicing, VAT, multi-currency, print-to-PDF | Inline (works offline) |
| `site.html` | One-page portfolio generator | Inline (works offline) |
| `analytics.html` | Cross-tool live dashboard | Inline (works offline) |
| `scheduler.html` | Booking + calendar | Estate (FallSlot) |
| `email.html` | Email lists + sequences | Estate (FallList) |
| `forms.html` | Intake forms | Estate (FallForm) |
| `proposals.html` | Quote + proposal generator | Estate (FallCarousel) |
| `legal.html` | 60 templates · contracts · LBAs | Estate (GroundLevel) |
| `social.html` | LinkedIn strategy + posting | Estate (FallPost) |

The 4 inline tools work fully offline. The 6 estate tools are linked from your fork but live on the canonical sovereign estate — they work when online. (Roadmap: full inline versions in v2.1.)

### Learn (`learn/`)
Five lessons, plain English, no MBA-speak:

1. **`start.html`** — Just got laid off, now what? The first 72 hours.
2. **`pricing.html`** — How to price yourself. Interactive day-rate calculator.
3. **`clients.html`** — How to find your first client. Warm-network method.
4. **`money.html`** — Invoicing, tax, getting paid. The 30% tax-set-aside rule.
5. **`grow.html`** — From 1 client to 10. The 6-10 ceiling, not 100.

### Config (`config.json`)
One file. Every tool reads from it.

```json
{
  "name": "Sarah Chen",
  "business": "SarahChen Consulting",
  "industry": "sales-ops",
  "currency": "GBP",
  "hourly_rate": 150,
  "api_provider": "anthropic",
  "api_key": "sk-ant-...",
  "payment_details": { "bank": "Monzo", "sort_code": "04-00-04", "account_number": "..." }
}
```

Change your rate once → every proposal and invoice updates.
Add an API key → the tutor becomes conversational, every AI feature unlocks.

---

## Cross-tool integration

Tools talk to each other over `BroadcastChannel('fall-signal')`:

- CRM marks a deal won → Accounts opens a pre-filled invoice
- Accounts marks an invoice paid → dashboard refreshes the revenue stat
- Any tool updates → analytics dashboard re-renders live

No middleware. No service to maintain. The browser tab is the bus.

---

## Going fully offline

The "Take it offline" tab in the hub:

1. Downloads the entire fork as a ZIP
2. You unzip to a folder or USB stick
3. Open `index.html` from anywhere — works from `file://`
4. The internet is now optional
5. Run forever without GitHub

Your config and tool data live in your browser's localStorage — they persist on the device. The download button also exports `config.json` separately so you can move between devices.

---

## Free · always · the philosophy

ExitEngine itself: **free forever**. Non-negotiable.

The whole point is helping people who just lost income. Charging them would be obscene.

Optional paid services (Simon's time, not the tools):

- Case review — £50 — review your situation, suggest strategy
- Custom letter / proposal drafting — £100 — for situations no template covers
- Coaching — £200/hr — complex multi-step cases

But £0 is always an option. The tools work the same whether you pay nothing or £200.

---

## Architecture choices

- **Single repo · fork-to-distribute**: the GitHub fork is the install + the marketing + the social proof
- **One config file**: every tool reads from one source of truth
- **`BroadcastChannel` mesh**: tools coordinate without a backend
- **`localStorage` persistence**: state survives reload, no signup
- **EU AI Act Article 12 audit shim baked in**: compliance posture by default
- **Vanilla JS, no framework**: each tool file is readable in a weekend
- **MIT license**: fork, modify, white-label, sell — just keep the philosophy

---

## What ExitEngine is NOT

- ❌ Not a job-board. The premise is you don't need another employer.
- ❌ Not a course. No 8-week programme, no certificates, no upsells.
- ❌ Not a SaaS. Nothing to subscribe to.
- ❌ Not an LLM wrapper. The tools work without AI. AI enhances.
- ❌ Not a productivity cult. Two posts a week is enough. Six clients is enough.

---

## Prime + constant

**Prime: 617** · the prime after fall-euaiact (607) and GroundLevel (613)
**Constant: κ = φ⁵** · the golden ratio to the fifth power · because the journey is five phases

---

## Sister tools in the estate

- [GroundLevel](https://github.com/sjgant80-hub/groundlevel) — sovereign legal toolkit · 60 templates · 12 modules
- [fall-euaiact](https://github.com/sjgant80-hub/fall-euaiact) — EU AI Act Article 12 compliance kit
- [fallpost](https://github.com/sjgant80-hub/fallpost) — sovereign LinkedIn engine
- [fallform](https://github.com/sjgant80-hub/fallform) — intake forms
- [falllist](https://github.com/sjgant80-hub/falllist) — email lists
- [fallslot](https://github.com/sjgant80-hub/fallslot) — scheduling

The whole estate at [ai-nativesolutions.com](https://ai-nativesolutions.com).

---

## License

MIT. Use freely. Fork freely. Sell freely if you must — but keep the LICENSE intact and the philosophy in the README.

---

> the law is public · the templates are simple · the jargon is the paywall
> remove the paywall · level the ground · fight back
> for the people · not the few
> the company was the middleman · the middleman is gone
> you're not unemployed · you're unblocked
> phase 1 wound · phase 2 shadow · phase 3 rebirth · phase 4 integration · phase 5 sovereign

**◊·κ=φ⁵**
