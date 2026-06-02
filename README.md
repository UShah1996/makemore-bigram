# makemore Bigram (Part 1)

Jupyter notebook progress for [Andrej Karpathy's *makemore* series](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhqnK) — building a character-level **bigram language model** on baby names, then preparing data for the neural-network version.

## What this repo covers (Part 1)

- Load the name dataset and inspect bigram counts
- Build a `27×27` count matrix `N` (26 letters + start/end token `.`)
- Visualize transition counts with matplotlib
- Sample new names from row-wise probabilities
- Add **Laplace smoothing** (`N + 1`) and resample
- Compute **log-likelihood** and average **negative log-likelihood** (cross-entropy) on the training set
- Build `(xs, ys)` integer tensors for the upcoming NN bigram model

## Project layout

| File | Description |
|------|-------------|
| `2026-04-29_makemore_bigram.ipynb` | Main notebook (Part 1) |
| `names.txt` | Training names ([Karpathy `makemore`](https://github.com/karpathy/makemore) dataset) |
| `requirements.txt` | Python dependencies |

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

Open `2026-04-29_makemore_bigram.ipynb` and run all cells from the project root so `names.txt` resolves correctly.

## Requirements

- Python 3.10+
- PyTorch
- matplotlib
- Jupyter

## Data attribution

`names.txt` comes from the [makemore](https://github.com/karpathy/makemore) repository (US baby names). See that repo for license and provenance.

## References

- [makemore playlist](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhqnK)
- [makemore GitHub](https://github.com/karpathy/makemore)

## License

MIT — see [LICENSE](LICENSE).
