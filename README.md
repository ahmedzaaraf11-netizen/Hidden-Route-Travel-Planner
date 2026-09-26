# The Hidden Route — AI-Assisted Travel Planner

A final year BCA project: a single-page web app that generates a day-by-day itinerary, a cost estimate, and locally-known "hidden gem" spots for a chosen destination and trip length.

**Live demo:** _add your GitHub Pages link here once enabled, e.g. `https://ahmedzaaraf11-netizen.github.io/hidden-route-travel-planner/

## What it does

- **Itinerary generation** — enter a destination and number of days, and the app builds a day-wise plan by distributing curated attractions across the trip, easing off on the final day.
- **Budget estimation** — a ledger-style breakdown (stay, food, local transport, activities) across three travel styles: Shoestring, Comfortable, and Premium, scaled to the number of days.
- **Hidden gems** — a small set of lesser-known spots per destination, shown as a clue behind a "wax seal" that the user clicks to reveal — the project's unique feature, meant to surface places a typical search engine or guidebook overview would miss.

## Tech stack

- HTML, CSS, and vanilla JavaScript — no frameworks, no build step, no dependencies to install
- Google Fonts (Fraunces + Inter) loaded via CDN
- Runs entirely in the browser as a single `index.html` file

## How it works (for the project report / viva)

The planner is **rule-based, not a live AI/LLM call**. Each destination has a hand-curated dataset (attractions, hidden gems, per-day cost by tier) stored as a JavaScript object in the file. On submit, the app:

1. Matches the typed destination against the dataset (with basic partial-match autocomplete).
2. Spreads that destination's attraction list across the requested number of days.
3. Multiplies the selected tier's per-day cost by the number of days for the budget ledger.
4. Reveals one or two hidden gems for that destination.

This keeps the app fully self-contained (works offline once loaded, no API key required) while still demonstrating personalization logic driven by user input — the "AI" framing refers to the recommendation/itinerary-building logic, not a connected language model.

## Destinations currently covered

Goa, Udaipur, Jaipur, Manali, Rishikesh, Munnar, Leh–Ladakh, Andaman, Varanasi, Pondicherry.

Adding a new destination only requires adding one more entry to the `DATA` object at the top of the `<script>` tag in `index.html` — no other code changes needed.

## Running it locally

No installation required.

1. Download `index.html` from this repository.
2. Double-click it, or open it in any browser (Chrome, Edge, Firefox).

## Project structure

```
├── index.html   # entire app — markup, styles, data, and logic in one file
└── README.md
```

## Possible extensions

- Replace the static dataset with a real places/hotels API for live pricing and attraction data.
- Add a small ML model or an LLM API call for destinations outside the curated list.
- Save generated itineraries (e.g. to browser local storage or a backend) so users can revisit past plans.
- Let users mark hidden gems as visited, or submit their own.

## Author

Built as a BCA final year project on AI-assisted travel planning.
