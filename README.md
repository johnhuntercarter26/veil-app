# Veil

**A privacy-first period and reproductive health tracker, and an experiment in whether a vibe-coded app can be genuinely secure.**

Veil is built almost entirely through AI-assisted ("vibe-coded") development on the
[Base44](https://base44.com) platform. But it's more than an app. It's a test of a
thesis. The common assumption is that vibe-coding trades away security for speed, that
apps built this way are inherently leaky. Veil is the counter-argument: an attempt
to build, and prove out, a vibe-coded application that handles some of the most sensitive
data there is (reproductive health) while holding to a real, defensible privacy standard.

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

- **Security is a first-class requirement, not an afterthought.** Every data feature is
  built and then verified against a simple standard: each user can only ever reach their own data.
- **Simplicity as a security strategy.** Collect as little as possible, and add features only
  when they earn their place. Less surface area means fewer places for mistakes to hide.
- **Verify, don't assume.** The codebase and its data rules are reviewed directly, not taken on faith.

An honest caveat, because a credible claim names its limits: "no issues found" is not
"provably secure," and self-review plus platform tooling is not a substitute for independent
professional audit. The thesis isn't "this is unbreakable." It's that "vibe-coded" and "genuinely
secure" are not mutually exclusive, and here's the work to back that up.

## What Veil does

- **Daily logging.** Track period days, flow, symptoms, sleep quality, mood, and private notes.
- **Calendar view.** See your cycle at a glance, with estimated period, fertile, and ovulation markers.
- **Cycle predictions.** Estimated period, fertile window, and ovulation days based on your history.
- **Insights.** Cycle-length trends, most-logged symptoms, and cycle history, computed from your own data.
- **Health tab.** Read-only wellness suggestions (nutrition, exercise, self-care) based on your estimated cycle phase.
- **Personalization.** Customizable symptom and mood lists, theme color, and a device-synced dark mode.
- **Privacy mode.** An on-screen shield that hides sensitive details at a glance.
- **Data control.** Export or delete your data from Settings.
- **Feedback.** A simple way for users to send suggestions.

## Privacy and security posture

This is where the thesis gets tested. The standard Veil holds to:

- **Per-user data isolation.** Every record is locked to its owner. A user can only
  read, edit, or delete their own data, and no admin or other account can reach it.
- **No anonymous access.** Health data is never readable by signed-out visitors or other accounts.
- **Data minimization.** The app stores only what it needs to function.
- **Auth handled by the platform.** Passwords are never stored or handled by the app; sign-in is managed by Base44.
- **Nothing sensitive on the device.** Cycle data is not persisted to local storage, and nothing sensitive is logged.
- **Secrets stay secret.** Keys and credentials live in the platform's secrets store, never in the codebase.
- **Routine verification.** The data rules and code are re-checked after any change that touches data.

## Built with

- **Base44** for the managed backend (database, auth, permissions) and AI-assisted builder
- **React** and **Vite**
- **Tailwind CSS**
- **TanStack Query** (`@tanstack/react-query`) for data fetching
- **date-fns** for date math
- **Recharts** for insights charts
- **lucide-react** for icons

## Status

**Active development.** Solo project, iterating one change at a time. Mobile-first, intended for App Store release.

## Progress so far

- [x] Core cycle logging, calendar, predictions, and insights
- [x] Read-only Health tab with phase-based wellness suggestions
- [x] Customizable per-user symptom and mood lists
- [x] Privacy mode applied consistently across all data screens
- [x] Data export (stripped to content fields, readable symptom labels, unencrypted-file warning)
- [x] Device-synced dark mode (defaults to light) with contrast pass on badges and banners
- [x] **Full data-layer security pass.** Every table locked to its owner; removed a legacy admin
      backdoor on cycle logs; verified no privilege-escalation path
- [x] **Full code-layer security review.** Every file reviewed or verified; data access relies on
      server-enforced per-user rules; auth defers to the platform; no secrets or sensitive logging found

## Roadmap

- [ ] **Complete data deletion.** "Delete all my data" should also clear custom symptom/mood lists;
      "delete account" should fully remove the account (needs a backend function)
- [ ] **Anonymous feedback.** Submit feedback without it being tied to the account (needs a backend function)
- [ ] **Health tab scope decision.** Keep read-only, or expand into new sections (would mean collecting new data)
- [ ] **Mobile and App Store readiness.** Native wrapper, privacy policy, store data declarations, mobile-specific review
- [ ] Polish pass: error handling on save/delete, minor display fixes
- [ ] Ongoing security re-checks after any new data feature
- [ ] Screenshots and demo
- [ ] License

## Development notes

This is a Base44-hosted app, so the backend (database, auth, permissions) is managed by
the platform rather than run locally. The code here mirrors the app's front end.

- Do **not** commit secrets. Keep API keys and credentials in Base44's secrets store.
- Environment and secret files should be listed in `.gitignore` and never pushed.

## License

_TBD._

---

*Last updated: 2026-06-10*
