# Veil

**A privacy-first period & reproductive health tracker — and an experiment in whether a vibe-coded app can be genuinely secure.**

Veil is built almost entirely through AI-assisted ("vibe-coded") development on the
[Base44](https://base44.com) platform. But it's more than an app: it's a test of a
thesis. The common assumption is that vibe-coding trades away security for speed — that
apps built this way are inherently leaky. Veil is the counter-argument. It's an attempt
to build, and prove out, a vibe-coded application that handles some of the most sensitive
data there is — reproductive health — while holding to a real, defensible privacy standard.

The evidence so far says it can be done.

> **Disclaimer:** Veil is for personal tracking and informational purposes only.
> Its predictions are estimates, not medical advice. It is not a contraceptive tool
> and should not be relied on to prevent or achieve pregnancy. Consult a healthcare
> professional for medical concerns.

---

## The thesis

Can an application be vibe-coded from end to end and still be secure enough to trust with
sensitive health data? Veil treats that as a question to answer with evidence, not assume.
The approach:

- **Security is a first-class requirement, not an afterthought** — every data feature is
  built and then verified against a simple standard: each user can only ever reach their own data.
- **Simplicity as a security strategy** — collect as little as possible, add features only
  when they earn their place. Less surface area, fewer places for mistakes to hide.
- **Verify, don't assume** — the codebase and its data rules are reviewed directly, not taken on faith.

An honest caveat, because a credible claim names its limits: "no issues found" is not
"provably secure," and self-review plus platform tooling is not a substitute for independent
professional audit. The thesis isn't "this is unbreakable" — it's "vibe-coded and genuinely
secure are not mutually exclusive, and here's the work to back that up."

## What Veil does

- **Daily logging** — track period days, flow, symptoms, sleep quality, mood, and private notes.
- **Calendar view** — see your cycle at a glance, with estimated period, fertile, and ovulation markers.
- **Cycle predictions** — estimated period, fertile window, and ovulation days based on your history.
- **Insights** — cycle-length trends, most-logged symptoms, and cycle history, computed from your own data.
- **Health tab** — read-only wellness suggestions (nutrition, exercise, self-care) based on your estimated cycle phase.
- **Personalization** — customizable symptom and mood lists, theme color, and a device-synced dark mode.
- **Privacy mode** — an on-screen shield that hides sensitive details at a glance.
- **Data control** — export or delete your data from Settings.
- **Feedback** — a simple way for users to send suggestions.

## Privacy & security posture

This is where the thesis gets tested. The standard Veil holds to:

- **Per-user data isolation** — every record is locked to its owner. A user can only
  read, edit, or delete their own data; no admin or other account can reach it.
- **No anonymous access** — health data is never readable by signed-out visitors or other accounts.
- **Data minimization** — the app stores only what it needs to function.
- **Auth handled by the platform** — passwords are never stored or handled by the app; sign-in is managed by Base44.
- **Nothing sensitive on the device** — cycle data is not persisted to local storage, and nothing sensitive is logged.
- **Secrets stay secret** — keys and credentials live in the platform's secrets store, never in the codebase.
- **Routine verification** — the data rules and code are re-checked after any change that touches data.

## Built with

- **Base44** — managed backend (database, auth, permissions) + AI-assisted builder
- **React** + **Vite**
- **Tailwind CSS**
- **TanStack Query** (`@tanstack/react-query`) for data fetching
- **date-fns** for date math
- **Recharts** for insights charts
- **lucide-react** for icons

## Status

**Active development** — solo project, iterating one change at a time. Mobile-first; intended for App Store release.

## Progress so far

- [x] Core cycle logging, calendar, predictions, and insights
- [x] Read-only Health tab with phase-based wellness suggestions
- [x] Customizable per-user symptom and mood lists
- [x] Privacy mode applied consistently across all data screens
- [x] Data export (stripped to content fields, readable symptom labels, unencrypted-file warning)
- [x] Device-synced dark mode (defaults to light) with contrast pass on badges/banners
- [x] **Full data-layer security pass** — every table locked to its owner; removed a legacy admin
      backdoor on cycle logs; verified no privilege-escalation path
- [x] **Full code-layer security review** — every file reviewed or verified; data access relies on
      server-enforced per-user rules; auth defers to the platform; no secrets or sensitive logging found

## Roadmap

- [ ] **Complete data deletion** — "delete all my data" should also clear custom symptom/mood lists;
      "delete account" should fully remove the account (needs a backend function)
- [ ] **Anonymous feedback** — submit feedback without it being tied to the account (needs a backend function)
- [ ] **Health tab scope decision** — keep read-only, or expand into new sections (would mean collecting new data)
- [ ] **Mobile / App Store readiness** — native wrapper, privacy policy, store data declarations, mobile-specific review
- [ ] Polish pass — error handling on save/delete, minor display fixes
- [ ] Ongoing security re-checks after any new data feature
- [ ] Screenshots / demo
- [ ] License

## Development notes

This is a Base44-hosted app, so the backend (database, auth, permissions) is managed by
the platform rather than run locally. The code here mirrors the app's front end.

- Do **not** commit secrets. Keep API keys and credentials in Base44's secrets store.
- Environment/secret files should be listed in `.gitignore` and never pushed.

## License

_TBD._

---

*Last updated: 2026-06-10*
