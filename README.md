# Tea Room Beverage Report (Dhivehi / English)

A bilingual (Dhivehi RTL / English LTR) staff tea-room consumption & sales report, built as a single self-contained `index.html` file.

## Files in this repo

```
index.html                    ← the page itself
Mv-Mohamed-Ali-Final.ttf      ← Dhivehi body font ("Mv Meemu Ali")
MvIzyanreethi-Bold.ttf        ← Dhivehi bold/heading font ("Mv Izyan Reethi")
```

**Keep all three files in the same folder** — the page loads the two `.ttf` files with a relative path (`url('Mv-Mohamed-Ali-Final.ttf')` etc.), so they must sit next to `index.html`, not in a subfolder, unless you edit the `@font-face` paths in the `<style>` block.

## What it does

- Toggle between English and Dhivehi with the pill switcher in the header (direction, fonts, number/date formatting, and all labels flip automatically).
- A searchable staff directory with totals.
- Click a staff member to see their itemized, month-grouped purchase history.
- All data is embedded directly in the page (`RAW_DATA` array in the script) — no backend or database needed.

## Publish it on GitHub Pages

1. Create a new repository on GitHub (e.g. `tea-room-report`).
2. Upload these three files to the root of the repo (or push them with git):
   ```bash
   git init
   git add index.html Mv-Mohamed-Ali-Final.ttf MvIzyanreethi-Bold.ttf
   git commit -m "Initial tea room report"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
5. Save. GitHub will give you a URL like `https://<your-username>.github.io/<repo-name>/` within a minute or two.

That's it — no build step, no dependencies to install (the page only pulls Google Fonts for the Latin typefaces `Fraunces`/`Karla`; the Dhivehi fonts are the local `.ttf` files bundled here, so Dhivehi text renders correctly even offline).

## Updating the data

To change staff names, entries, or rates, edit the `RAW_DATA`, `RATES`, and `NAMES_DV` (Dhivehi name mapping) constants near the top of the `<script>` block in `index.html`.
