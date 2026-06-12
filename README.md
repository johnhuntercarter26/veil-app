# Veil

Privacy-first period and reproductive health tracker.

## What Veil is

Veil is a private cycle and reproductive health tracking app. It is built to keep sensitive health data tied to the person it belongs to and no one else. The guiding idea is simple. Collect as little as possible, lock down what is collected so each user can only ever see their own data, and keep the app small enough that mistakes have nowhere to hide.

## The thesis

Veil is also an experiment with a clear claim behind it. An app built largely with AI assisted development can be made genuinely private and secure, as long as every change is reviewed deliberately rather than trusted on faith. This repository documents that work in the open as evidence that it can be done, not as a neutral case study.

A recurring lesson sits at the center of the project. The same AI that writes the code is not a reliable judge of whether that code is safe. Reviewing the actual files, rather than trusting automated summaries, is what closes the gap.

## Current status

In active development. Core tracking, predictions, calendar, and settings are working. A full review of the data layer and the application code has been completed, and the most recent round of fixes has been verified against live data. The app is not yet submitted to the App Store.

## What has been done

Data access is locked down. Every data table restricts access so that a user can reach only their own records, and any table that should never be read back by users is write only by design. Anonymous access and cross account access to health data are closed.

Data handling has been tightened. The app collects only what it needs, keeps no secrets in plain text, and does not log or persist sensitive data to the device. The data export feature produces a clean, readable copy that leaves out internal system fields.

The delete my data flow now fully honors its promise. Choosing to delete all data removes every record the user owns across all relevant tables and resets the account to a blank state, the same as a fresh start. This was verified directly against the database before and after deletion.

Symptom records are now stored in a readable form. This corrected a display problem where logged symptoms showed up as internal codes, and it made the data export human readable as a result.

Dark mode readability was fixed. Theme handling was consolidated into a single shared routine, so color choices now apply correctly in both light and dark mode and cannot drift out of sync between screens.

## What is left to do

True account deletion and anonymous feedback. Both depend on backend functions that require a paid platform plan. The current flow clears all user data, and full account removal is the next step once that plan is in place.

A small set of polish and consistency items remain. These include a duplicate seeding edge case in the default options, a built screen that is not yet linked into navigation and needs to be either wired in or removed, and a minor theme refresh case when switching between light and dark mode.

Publish this repository and prepare for App Store submission.

## Privacy stance

Health data in Veil is tied to a single account and is not sold or used to target advertising. Where the platform gives the app owner visibility into stored data, that reality is documented plainly rather than hidden. The aim is honesty about what is and is not possible on the current stack, alongside a steady effort to keep what the app can see to a minimum.
