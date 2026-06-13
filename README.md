# Veil

Privacy-first period and reproductive health tracker.

## What Veil is

Veil is a private cycle and reproductive health tracking app. It is built to keep sensitive health data tied to the person it belongs to and no one else. The guiding idea is simple. Collect as little as possible, lock down what is collected so each user can only ever see their own data, and keep the app small enough that mistakes have nowhere to hide.

## The thesis

Veil is also an experiment with a clear claim behind it. An app built largely with AI assisted development can be made genuinely private and secure, as long as every change is reviewed deliberately rather than trusted on faith. This repository documents that work in the open as evidence that it can be done, not as a neutral case study.

A recurring lesson sits at the center of the project. The same AI that writes the code is not a reliable judge of whether that code is safe. Reviewing the actual files and inspecting the real stored data, rather than trusting that something looks correct, is what closes the gap. More than one issue here was a feature that appeared to work on the surface while behaving differently underneath, and only a direct look at the live data revealed the truth.

## Current status

In active development.

Recent work has focused on making the app's promises literally true. Data deletion now fully clears every piece of a user's data rather than leaving fragments behind, and the deletion action no longer claims more than it actually does. Settings now save reliably and the app reflects saved changes immediately, which was traced to a stale profile cache rather than a failed write. Each fix was verified against the live data, not just the code.

## Privacy stance

Health data in Veil is tied to a single account and is not sold or used to target advertising. Where the platform gives the app owner visibility into stored data, that reality is documented plainly rather than hidden. The aim is honesty about what is and is not possible on the current stack, alongside a steady effort to keep what the app can see to a minimum.

## Roadmap

- True account deletion, so closing an account removes the login itself and not only its data. This depends on backend functions available on a paid platform tier.
- Genuinely anonymous feedback, also dependent on backend functions.
- Ensure in app notices, including the warning that an exported file is unencrypted, are always shown to the user.
- Resolve readable symptom names in exported data.
- Publish to the App Store.

## Notes for contributors

- Do not commit secrets. Keep API keys and credentials in the platform secrets store.
- Environment and secret files should be listed in `.gitignore` and never pushed.

## License

TBD.

---

Last updated: 2026-06-13
