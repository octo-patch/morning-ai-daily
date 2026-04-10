# Morning AI Daily - Project Guidelines

## Adding a new daily report

When creating a new daily report:

1. **Create the report file** in `YYYY-MM/YYYY-MM-DD.md` with this frontmatter:
   ```yaml
   ---
   layout: report
   title: "Morning AI Daily — YYYY-MM-DD"
   date: YYYY-MM-DD
   summary: "One-line summary of key highlights"
   highlights:
     - type: Model
       entity: "Company Name"
       title: "Short headline"
       score: 8.5
       summary: "One-sentence description"
   stats:
     total: 20
     models: 4
     products: 8
     benchmarks: 7
     funding: 1
   ---
   ```

2. **Required frontmatter fields:**
   - `layout: report` — assigns the report layout
   - `title` — display title for the page
   - `date` — YYYY-MM-DD format (unquoted), used for sorting and RSS feed
   - `summary` — one-line summary shown on homepage and in README
   - `highlights` — array of news items (see rules below)
   - `stats` — count by type from the Statistics Summary table

3. **Highlights array rules:**
   - Include ALL items from the report (7+ from TLDR, 5-6 from Regular, 3-4 from Minor)
   - `type` must be one of: Model, Product, Benchmark, Funding (case-sensitive)
   - `score` must be an unquoted number (e.g. `8.5` not `"8.5"`)
   - `entity` is the company/organization name
   - `title` is a short headline (no entity prefix)
   - `summary` is one sentence

4. **DO NOT modify `index.md`** — it uses Liquid templating to automatically render cards from report frontmatter data. Any new report with `layout: report` will appear automatically.

5. **Report body markdown** — keep the full report content as-is below the frontmatter. The body is rendered on the detail page.
