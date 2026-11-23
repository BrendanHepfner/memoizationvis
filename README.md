# Memoized recursion: start at n−1, or start at 0?

An interactive visualizer for CSCI 332 (Advanced Data Structures and Algorithms) that compares two ways of writing the same memoized recursion:

- **Start at n−1:** the first call is at the end and the recursion works back toward the start. Each cached value means "ways to get *here* from the start."
- **Start at 0:** the first call is at the start and the recursion works forward toward the end. Each cached value means "ways to get from here to the end."

Both always give the same answer. The page runs them side by side, in lockstep, on the same problem so you can see where they differ: which states each one explores, how much work is wasted on dead ends, and which future questions each cache can still answer.

## Examples

| Family | Tie | Start at n−1 wins | Start at 0 wins |
|---|---|---|---|
| Maze (count right/down routes) | Open maze | Dead-end area | Cut off from S |
| Stepping stones (hop 1 or 2) | No gaps | Gap near the end | Gap near the start |
| Word break (count splits) | `aaaaaaaa` | `aaaaaaaaab` | `baaaaaaaaa` |
| Several questions, one cache | | Same start, 5 goals | Same goal, 5 starts |

Every example can be edited (toggle walls, remove stones, type your own string and dictionary). A scoreboard compares call counts across all examples.

## Features

- Step, play, pause and scrub through both runs at once
- The code for each direction, with the current line highlighted and the differences marked
- Call stack, cache hits, dead ends and call counts for each side
- Hover any state to compare what each side stored there
- A head-to-head table and a short explanation of when to pick each direction

## Running it

There is nothing to install or build. The whole site is one self-contained file, `index.html`, with no external libraries.

- **Locally:** open `index.html` in any modern browser.
- **GitHub Pages:** push this repository to GitHub, then go to **Settings → Pages**, set **Source** to "Deploy from a branch", and pick the `main` branch and the `/ (root)` folder. The site will be published at `https://<your-username>.github.io/<repo-name>/`.

## Project structure

```
index.html   the whole site: HTML, CSS and JavaScript in one file
README.md    this file
.gitignore   ignores OS and editor clutter
```
