# AI Readiness Score

A single-page web prototype: a **10-question grader** that scores any local business 0–100 on AI/automation readiness.

- 10 multiple-choice questions, one at a time, with a progress bar
- 5 categories (Lead Response, Booking & Scheduling, Follow-up & Nurture, Reviews & Reputation, Data & Insights)
- Animated score reveal (count-up + ring), letter grade, per-category animated bars
- Top-3 personalized recommendations (drawn from the lowest-scoring categories)
- "Copy my report" clipboard summary, embeddable badge snippet, Retake button

## How to run

Option 1 — just open it:
```
double-click index.html
```

Option 2 — serve over HTTP:
```bash
cd ~/workspace/inventions/ai-readiness-score && python3 -m http.server 8000
```
Then open http://localhost:8000 in a browser.

## Demo steps

1. Enter a business name and pick a vertical (clinic / hotel / real estate / other), then **Start the assessment**.
2. Answer the 10 questions (← Back works to change an answer).
3. Watch the score count up, then review the category bars and top-3 fixes.
4. Try **Copy my report** (clipboard text summary) and **Copy badge code** (pasteable HTML badge).
5. Hit **Retake** to run it again.

## Notes

- **Scoring is heuristic and client-side.** Each answer maps to 0–3 points; categories are weighted equally (mean of the five category percentages). Grades: 90+ AI-Ready, 70+ Almost There, 50+ Leaking Leads, 30+ Manual Mode, below 30 Urgent.
- **No data leaves the browser.** No network calls, no analytics, no external CDNs, no build step, no API keys. It works over `file://` too.
- Dependency-free: one `index.html` (inline CSS + vanilla JS), this `README.md`.
