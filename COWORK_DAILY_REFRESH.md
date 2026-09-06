# Disruptors — daily refresh (Cowork)

Paste this as a recurring weekday Cowork task. Point it at the repo folder on the iMac.

---

You are updating `data.json` for AJ's Disruptors app (repo folder: `~/Disruptors`). Do the whole job, then commit and push. Don't ask questions.

**Job**
1. Read the current `data.json`. Keep its exact schema:
   ```
   { "updated": "YYYY-MM-DD", "seed": false, "categories": [
     { "id", "name", "color", "trend": "up|down|flat", "heat": 0-100,
       "gaps": ["..."], "companies": [
         { "name", "what", "stage", "signal", "trend", "why", "source" } ] } ] }
   ```
2. For every category, web-search the last 7 days for: funding rounds, launches, retail expansion, acquisitions, layoffs, shutdowns. Sources: TechCrunch, Axios Pro Rata, Modern Retail, Retail Dive, Food Dive, The Information, Crunchbase News, Business of Fashion, Fast Company, X posts from founders/VCs.
3. Focus rule: **smaller disruptors only** — founded in the last ~10 years, private or recently public, under ~$5B. Skip incumbents (Coca-Cola, Home Depot, Uber, etc.) unless their move directly threatens a disruptor, and then mention it inside that company's `signal`, not as its own entry.
4. Per category keep the 3–6 most relevant companies. Replace stale ones. Each `signal` = the newest concrete fact (with a date if you have it). Each `why` = one line on why AJ should care. `source` = publication name or URL.
5. Rewrite `gaps` (2–4 per category): what's still broken, underserved, or badly branded in that market this week. Be specific — these are the ideas AJ will act on.
6. Set `trend` and `heat` per category from this week's news volume and momentum. Heat 90+ means capital and attention are pouring in; under 40 means it's cooling.
7. Add a new category if a real new market shows up (e.g. "Humanoid robots"); pick an unused hex color. Remove a category only if it's been dead for a month.
8. Set `updated` to today and `seed` to `false`. Validate the JSON parses.
9. `git add data.json && git commit -m "refresh YYYY-MM-DD" && git push`. Netlify redeploys automatically.

**Output back to AJ**: 5 bullets max — the biggest moves of the day and any new gap worth a business.
