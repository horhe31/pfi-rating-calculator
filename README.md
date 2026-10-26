# PFI Rating Calculator

A browser calculator for the student-review rating component of a monthly ranking.

**Live app:** https://horhe31.github.io/pfi-rating-calculator/

## Calculate a rating

1. Select the ranking month. The displayed cutoff is the previous month's 26th through the selected month's 25th, UTC+8, using review submission time.
2. Enter received reviews for each star rating.
3. Enter rejected or deleted reviews in Excluded, counting each excluded review once.
4. Read the counted reviews, five-star share, base points, low-star deduction, and final rating.
5. Use the slider to preview extra five-star reviews. Copy or save the summary to keep your calculation.

The formula is:

`Rating = 30 × (counted 5-star reviews / all counted reviews) − 3 × (counted 1-star + counted 2-star reviews)`

The app starts with zero counts and the current month in UTC+8. The example buttons use sample counts and preserve your selected month.

## Scoring limits

This is an independent planning tool. The formula was reconstructed from a September 2026 ranking. Confirm the formula, cutoff, eligibility, rounding, no-review default, and any zero-floor policy for each future ranking month. Selecting a month does not update or verify the scoring policy. The app does not calculate overall PFI or rank and does not retrieve teacher records.

Exact rational arithmetic is used and the final score is rounded to two decimals, with exact halves rounded away from zero. An official result may differ by 0.01 in tie cases. Negative results are preserved. With no counted reviews, the app shows no calculated rating.

## Privacy and offline use

The calculator has no backend, external libraries, analytics, or automatic input storage. Counts and the optional name stay in your browser. Copy/save only when you choose to do so. Inputs reset when the page reloads.

Download index.html and open it in a modern browser to use it offline. The hosted page needs an internet connection to load.

## Maintain and test

GitHub Pages publishes the root of the main branch. Edit index.html and commit the change to update the site. No build or package installation is needed.

Run the calculation checks with Node.js:

`node tests.cjs`

Keep this scoring notice up to date if the official monthly rules change.
