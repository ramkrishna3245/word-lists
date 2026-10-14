# 5-Letter Word Lists (A–Z)

Free, open word-list data for 5-letter word games — the same lists that power the tools on **[AnyWordSolver](https://anywordsolver.com/)**.

- **12,478** accepted 5-letter words (guess-acceptance pool)
- **1,170** curated everyday answer words
- Split by first letter A–Z
- Plain text + JSON, no dependencies, MIT licensed

---

## What's in here

| File | Contents |
| --- | --- |
| `5-letter-words.txt` | All 12,478 valid 5-letter words, one per line (uppercase, A–Z sorted) |
| `5-letter-answer-pool.txt` | 1,170 curated common 5-letter words (good answer candidates) |
| `5-letter-words.json` | The full list as a JSON array |
| `by-first-letter/a.txt` … `z.txt` | The full list split by starting letter |
| `LICENSE` | MIT |

---

## Quick start

**JavaScript / Node**

```js
const words = require('fs')
  .readFileSync('5-letter-words.txt', 'utf8')
  .trim()
  .split('\n');

// every accepted 5-letter word
console.log(words.length); // 12478

// filter by pattern, e.g. _ A _ _ E
const pattern = /^.[A].(.)[E]$/i;
console.log(words.filter(w => pattern.test(w)).slice(0, 10));
```

**Python**

```python
words = open("5-letter-words.txt").read().split()

# words starting with "ST"
print([w for w in words if w.startswith("ST")][:10])

# candidates matching _A__E
import re
print([w for w in words if re.fullmatch(r".A..E", w)][:10])
```

---

## Playable tools that use this data

If you want the interactive versions rather than the raw lists:

- **[Word Finder](https://anywordsolver.com/word-finder.html)** — filter by pattern, included and excluded letters
- **[Wordle Solver](https://anywordsolver.com/wordle-solver.html)** — enter your green / yellow / grey tiles
- **[5-Letter Words A–Z](https://anywordsolver.com/5-letter-words.html)** — browse the lists by starting letter
- **[Anagram Decoder](https://anywordsolver.com/anagram-decoder.html)** — decode jumbled letters and phrases
- **[Word Scramble Solver](https://anywordsolver.com/word-scramble-solver.html)** — unscramble any letters, grouped by length
- **[Spellie](https://anywordsolver.com/spellie.html)** — Spelling Bee–style helper with pangrams and ranks
- **[All games](https://anywordsolver.com/word-games.html)** — Wordle-style, Connections, Strands, Sudoku, Boggle and more

All of the tools above are free and run in the browser with no login.

---

## Data notes

- Words are **uppercase**, sorted **A–Z**, one per line, `\n` line endings.
- The acceptance list is intentionally broad (it includes rarer valid words); the answer pool is the smaller curated list of everyday words.
- No proper nouns, no punctuation, no whitespace.

## License

MIT — see [LICENSE](LICENSE). Use it in your own games, bots or tools, commercially or otherwise.
