# The Macro Meal Mapper

Student tool for the **Watch the Scale Drop** course. One static page, no build step, no dependencies.

- Live at: `https://learn.coachnehanautiyal.com/macro-meal-mapper/`
- Source: `macro-meal-mapper/index.html` (the entire tool — HTML, CSS, JS, and all meal data in one file)

© Neha Nautiyal LLC. Not licensed for reuse or redistribution.

## Updating the tool

Edit `macro-meal-mapper/index.html`, commit to `main`, done — GitHub Pages republishes automatically in ~1 minute. Same URL, nothing for students to do. Their saved maps (browser localStorage) are untouched.

## Adding a meal (the rules)

All meals live in the `MEALS` array inside `index.html`. To add one:

1. Copy an existing meal block as your template (search for `"Tofu bhurji wrap"` to find the first one).
2. **Append it at the END of the `MEALS` array** — never insert in the middle. Meal IDs are positional; inserting mid-array scrambles students' saved preferences.
3. Fields: `s` slot (b/l/s/d/t) · `n` name · `short` grid label · `srv` what 1 serving is · `lvl` diet level (0 veg, 1 +eggs, 2 +fish, 3 +chicken/turkey, 4 +beef) · `gf`/`df` flags · `fb` fiber grams · `tags` flavors · `prots` protein keys · `comps` components as `[name, amount, cal, P, C, F]` · `steps` directions · `tip` your voice.
4. If the meal is no-cook or a big cooking job, add its `short` name to the `EFF0` or `EFF2` set just below the array (default is "15 min").

Or the easy way: mark recipes "Mapper? Y" in the recipe Google Sheet and ask Claude to "sync the meal bank" — it reads the sheet, builds the cards, and preps the commit.

## MacrosFirst share links (future)

Each meal can carry an `mf: "https://..."` share URL — when present, the card shows a one-tap "Log it in MacrosFirst" button. Build the meal in the MacrosFirst app (Kitchen → Meals), copy its share link, paste into the meal's block, commit.
