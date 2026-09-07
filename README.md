# Quiggly's Cookbook

62 recipes as a single self-contained HTML page. 59 transcribed from the handwritten card box, plus 2 from the to-do sticky note and 1 added from the web. None of those 3 are on cards yet.

## Files

- `index.html` — the whole site. Data is embedded, no build step, no server. Double-click it and it works.
- `recipes.json` — the same recipes as plain data, if you'd rather edit them there.

## Putting it on GitHub Pages

1. Make a new repo named `quigglys-cookbook`.
2. Drop `index.html` in the root and push.
3. Repo → Settings → Pages → Source: **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Two minutes later it's live at `https://<your-username>.github.io/quigglys-cookbook/`.

## What the site does

**Browse** — every recipe, alphabetical. Search hits titles, ingredients, tags, and instruction text.

**Filters** — collapsed by default so recipes stay above the fold. Six groups (protein, dish, cuisine, method, effort, vibe), and recipes carry multiple tags, so Chicken Tortilla Soup shows up under *soup*, *chicken*, *beans*, and *mexican*.

**What can I make?** — add what's in your fridge and every recipe gets ranked by how much of it you already cover. Each card shows a percentage, what you have, and what's missing. Two toggles: assume you have basics (salt, oil, garlic, butter), and only show recipes you can make right now.

Your pantry list, theme, and toggles persist in the browser via localStorage.

## Adding a recipe

Edit the JSON inside the `<script id="data">` tag near the bottom of `index.html`. The shape:

```json
{
  "title": "Recipe Name",
  "tags": ["chicken", "soup", "weeknight"],
  "ingredients": ["1 lb chicken thigh", "Sauce: 2 tbs soy sauce"],
  "instructions": ["Do the first thing", "Then the second"],
  "keys": ["chicken thigh", "soy sauce"],
  "staples": ["salt", "olive oil"],
  "facets": {"Protein": ["chicken"], "Dish": ["soup"], "Effort": ["weeknight"]},
  "serves": "4"
}
```

`keys` is what the pantry matcher scores against, `staples` is what it ignores when the "assume I have basics" box is checked. Prefix an ingredient with `Label:` to group it visually (see Chicken Tikka Masala).

## Known gaps

Five cards had blank backs, so no method was ever written down. Those show a single "Combine all ingredients." step:

- Bolognese a la Quiggly (Patsy Spaghetti)
- Creamy Sun Dried Tomato Pasta
- Caesar Dressing
- Agi's Dressing
- Chimichurri Sauce

Transcription is verbatim from the cards with light cleanup: abbreviations kept (EVOO, S&P, Dan-O's), crossed-out text dropped, margin notes folded into the ingredient list.

## The two from the sticky note

Neither was ever on a card. Both are flagged in-app with a note saying where they came from.

**Gnocchi Sausage Soup** — The Everyday Cookbook version, as the note specified. The original calls for beef or chicken bone broth, so it uses chicken, and the garlic is doubled to 8 cloves per "w/ more garlic & chicken broth."

**Feta & Cherry Tomato Pasta Bake** — combined from three versions. The whole roasted garlic head and block feta in brine come from The Greek Foodie, the finishing broil from Alexandra's Kitchen, the pasta-water toss from Feel Good Foodie. Calabrian chilis and shallot added to match how the rest of the box cooks.
