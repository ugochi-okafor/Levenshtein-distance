# Levenshtein Distance with Vowel Weights

This project implements the Levenshtein edit distance in Python using a dynamic programming approach, with an optional extension to weight vowel substitutions differently.

## Features

- Standard Levenshtein distance between two strings (insertions, deletions, substitutions).
- Optional `vowel_weight` parameter:
  - When both characters are vowels (ASJP vowels: 3, a, e, E, i, o, u), substitutions cost `vowel_weight` (default 1.0).
  - All other edits cost 1.0.
- Backwards compatible. If `vowel_weight` is not provided, the function behaves like the standard Levenshtein distance.

## Files

- `similarity.py` – implementation of the `levenshtein_distance` function.
- `testspass.py` – unit tests for the standard version.
- `testsdistinction.py` – unit tests for the extended vowel-weight version.

## Requirements

- Python 3.x

### Optional: create a virtual environment
bash
python3 -m venv venv
source venv/bin/activate

### Running tests
```bash
python3 -m unittest testspass.py
python3 -m unittest testsdistinction.py
```
## Example
```python
from similarity import levenshtein_distance

print(levenshtein_distance("intention", "execution"))
print(levenshtein_distance("tri", "trEd", vowel_weight=0.5))  # returns 1.5
```

This project was developed as part of the Introduction to programming course at Stockholm University, and graded with distinction.
