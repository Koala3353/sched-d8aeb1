# AISIS Enlistment Portal (1st Sem SY 2026–2027)

This repository contains a single-file web app (`index.html`) that helps plan enlistment on AISIS by combining:

- pasted AISIS pre-enlistment content,
- your current/taken classes,
- blocked personal time,
- ranked section priorities,
- and live slot availability from embedded schedule data.

## What the app does

The portal has 3 tabs:

1. **Paste**
   - Paste copied text from AISIS **Enlist in Class**.
   - Parses `Subject + Section` pairs and marks them as taken.
   - Shows unmatched lines and lets you manually add missing sections.
   - Includes fallback inputs for pre-enlisted subjects.

2. **Planner**
   - Generates best schedule combinations for unsatisfied manual subjects.
   - Avoids time conflicts with taken classes and blocked windows.
   - Scores combinations using priority order, professor tier, and free slots.
   - Shows a weekly grid, alternatives list, and enlistment cheat sheet.
   - Supports one-click status updates: **✓ got it** and **⊘ full**.

3. **Settings**
   - Set profile filters (e.g., PE section gender filter).
   - Configure maximum back-to-back class chains.
   - Add and reorder priority lists (THEO+NSTP pairs, FLC, PATHFit).
   - Add blocked time windows.
   - Export/import settings JSON.
   - Upload a refreshed schedule CSV.

## Data and storage

- Schedule classes, priorities, pairings, reviews, and subject metadata are embedded inside `index.html` (`<script id="portal-data">`).
- User state is persisted in `localStorage` using key `aisis-portal-v1`.
- Uploaded CSV data is remapped against saved state by `subject + section`.

## How to run

No build step is required.

1. Open `index.html` in a browser.
2. Use the **Paste** tab first to load existing enlistments.
3. Switch to **Planner** and pick from suggested combinations.
4. Tune constraints and priorities in **Settings** as needed.

## Notes

- This is an offline/static tool designed for quick enlistment-day decision support.
- Always verify final slot availability and pairings in AISIS before submitting enlistment.
