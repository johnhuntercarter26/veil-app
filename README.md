Veil
A privacy-first period & reproductive health tracker.
Veil is a menstrual and reproductive health tracking app built with a privacy-first
philosophy: collect as little as possible, and make sure each person can only ever
access their own data. It's built on the Base44 platform.

⚕️ Disclaimer: Veil is for personal tracking and informational purposes only.
Its predictions are estimates, not medical advice. It is not a contraceptive tool
and should not be relied on to prevent or achieve pregnancy. Consult a healthcare
professional for medical concerns.


What Veil does

Daily logging — track period days, flow, symptoms, sleep quality, mood, and private notes.
Calendar view — see your cycle at a glance month to month.
Cycle predictions — estimated period, fertile window, and ovulation days based on your history.
Personalization — customizable symptom and mood lists, and a device-synced dark mode.
Feedback — a simple way for users to send suggestions.

Privacy & security posture
Privacy isn't a feature here, it's the foundation:

Per-user data isolation — every record is locked to its owner. A user can only
read, edit, or delete their own data.
No anonymous access — health data is never readable by signed-out visitors or other accounts.
Data minimization — the app stores only what it needs to function.
Secrets stay secret — keys and credentials live in the platform's secrets store, never in the codebase.
Routine security scans — the app's permissions are re-checked after any change that touches data.

Built with

Base44 — managed backend (database, auth, permissions) + AI-assisted builder
React + Vite
Tailwind CSS
TanStack Query (@tanstack/react-query) for data fetching
date-fns for date math
lucide-react for icons

Status
🚧 Active development — solo project, iterating one change at a time.
Progress so far

 Core cycle logging, calendar, and prediction features
 Customizable per-user symptom and mood lists
 Device-synced dark mode (defaults to light) with contrast pass on badges/banners
 Reduced decorative clutter while keeping functional markers
 Security hardening — tightened data-access rules so each user is fully scoped
to their own records; verified isolation across all data tables; confirmed
account-role protections

Roadmap

 Health tab — expanded sections for exercise, nutrition, self-care, and intimate health
(open question: read-only info vs. collecting new user data — decides the privacy approach)
 Anonymous feedback — let users submit feedback without it being tied to their account
(pending backend functions)
 Ongoing security re-scans after any new data feature
 Screenshots / demo
 License

Development notes
This is a Base44-hosted app, so the backend (database, auth, permissions) is managed by
the platform rather than run locally. The code here mirrors the app's front end.

Do not commit secrets. Keep API keys and credentials in Base44's secrets store.
Environment/secret files should be listed in .gitignore and never pushed.

License
TBD.

Last updated: 2026-06-09
