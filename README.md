# PrepFlow

PrepFlow is a personal dashboard I built to keep placement prep from turning into scattered notes, half finished spreadsheets, and forgotten revision topics. It tracks a daily routine, a study plan, whiteboard and revision topics, and shows all of it against a calendar so progress (or the lack of it) is hard to ignore.

It is a static site. No backend, no sign in, no accounts. Everything runs in the browser and saves to localStorage.

## What it does

- Shows your current focus block for the day and lets you mark it done or skip it
- Tracks a routine and a longer term study plan, both loaded from editable JSON files
- Lets you mark whiteboard and revision topics as mastered
- Renders a calendar view so you can see completed, skipped, and overdue days at a glance
- Exports your logs and mastery data as a JSON file, and can import it back
- Optionally auto loads a saved snapshot from a `progress/progress.json` file if you keep one in the repo

## Project structure

```
index.html      markup only
css/styles.css  all styling
js/app.js       app logic: loading data, rendering, state, calendar, timers
json/           the actual content: routine, study plan, whiteboard and revision topics
progress/       optional saved snapshot for auto loading progress on startup
```

The JSON files are separate from the code on purpose. Editing your routine or study plan means editing a JSON file, not touching any HTML or JavaScript.

## Running it

Because `app.js` fetches the JSON files, opening `index.html` directly (file://) will not work due to browser CORS restrictions. Serve the folder locally instead:

```bash
python3 -m http.server 8000
```

then open `http://localhost:8000`.

It also works as is on GitHub Pages, since that serves everything over https.

## Why it exists

Most planners are either too generic or too rigid. This one is built around one specific goal, placement prep, with just enough structure (routine, study plan, mastery tracking) to keep it honest, and just enough flexibility (plain JSON, no database) to reshape it as the plan changes.
