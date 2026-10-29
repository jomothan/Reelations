# Reelations

A daily movie puzzle. Find four groups of four movies that share something in common. You can make four mistakes.

**Play:** https://jomothan.github.io/Reelations/

## How it works

- Every day has a new puzzle, and everyone gets the same one on the same date.
- Groups are color-coded by difficulty: yellow (easiest), green, blue, red (hardest).
- Groups are based on things like genre, director, lead actor, production company, release year, or wordplay in the title (a color, number, animal and so on).
- When you finish, you can copy an emoji grid of your guesses to share.

## About the site

The whole game is one static file, `index.html`. The puzzles are generated ahead of time and built into the page, so there is no server or database. Your progress is saved in your browser.

## Rebuilding the puzzles

The puzzles come from the TMDB 5000 movie dataset, which is not included in this repo. To regenerate them, download the two CSVs into a `data/` folder and run:

```
python generate_puzzles.py \
  --movies data/tmdb_5000_movies.csv \
  --credits data/tmdb_5000_credits.csv \
  --start 2026-10-29 --min-votes 600 --seed 7 \
  --template game_template.html --html-out index.html
```

Requires Python 3 and pandas. Change `--start` and `--seed` when generating a new batch so puzzles don't repeat.

## Credits

Movie data from [The Movie Database (TMDB)](https://www.themoviedb.org/). This product uses TMDB data but is not endorsed or certified by TMDB.
