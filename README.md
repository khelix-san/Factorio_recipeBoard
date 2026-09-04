# Factorio Recipe Board

A small local web app for browsing every recipe in **Factorio 2.0** (base game, no Space Age expansion), grouped into the game's own categories, with the ability to pin the recipes you use most so you always have them at hand.

No installation, no build step, no dependencies: a single HTML file you can open with a double-click.

## Features

- Full recipe list (214 recipes), grouped by category exactly as in the game: Logistics, Production, Intermediate products, Combat, Fluids.
- Official item icons next to the recipe title and next to every ingredient/product.
- Pin/unpin favorite recipes, with a dedicated tab to find them instantly.
- Search by recipe name.
- Click any ingredient or product to jump straight to the recipe that produces it.
- Light/dark theme.
- Interface available in 5 languages: **English (default)**, Italian, German, Spanish, French.
- Favorites are saved automatically in the browser (localStorage), and can also be exported/imported as a JSON file.

> **Note on languages:** only the app's interface (buttons, tabs, labels) is translated. Item and recipe names are kept in English, since that's the language of the underlying game data itself.

## How to use it

### Option A — just open it (simplest)

1. Download this repository (or the ZIP).
2. Keep these three files together in the same folder: `index.html`, `factorio_recipes.csv`, `icons.webp`.
3. Open `index.html` in your browser.

This works out of the box: the app has a built-in fallback copy of the recipe data, so it runs even when opened directly as a `file://` page, where browsers usually block loading local files via `fetch`.

### Option B — run it through a local server (optional, recommended if you plan to edit the CSV)

Opening the file directly always uses the recipe data embedded inside `index.html`. If you'd rather have the app read `factorio_recipes.csv` live (handy while editing it), serve the folder with a tiny local web server instead:

```bash
# from inside the project folder
python3 -m http.server 8000
```

Then open your browser at:

```
http://localhost:8000
```

(On Windows, if `python3` isn't recognized, try `python -m http.server 8000` instead.)

Any edits you make to `factorio_recipes.csv` will now show up on a page refresh, no need to touch `index.html`.

## File structure

| File | Contents |
|---|---|
| `index.html` | The application (HTML + CSS + JS, no framework) |
| `factorio_recipes.csv` | The recipe database |
| `icons.webp` | Sprite sheet with the item icons |

## Data

Recipes and icons were extracted from the open-source dataset of [FactorioLab](https://github.com/factoriolab/factoriolab), itself based on the official Factorio 2.0 game files.

## Credits

This project came out of a conversation with [Claude](https://claude.ai) (Anthropic): the idea, requirements, and decisions are mine, while the code and the data extraction/cleanup were built together with the AI, step by step, iterating until reaching this version.

## License

Personal/hobby use. Factorio, its assets, and its icons are the property of [Wube Software](https://factorio.com).
