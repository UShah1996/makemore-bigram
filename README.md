# makemore Bigram

[![Notebook CI](https://github.com/UShah1996/makemore-bigram/actions/workflows/notebook.yml/badge.svg)](https://github.com/UShah1996/makemore-bigram/actions/workflows/notebook.yml)

Learning project following [Andrej Karpathy's *makemore* series](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhqnK): a character-level **bigram language model** on baby names.

**Repository:** [github.com/UShah1996/makemore-bigram](https://github.com/UShah1996/makemore-bigram)

## What this repo covers (Part 1) — done

- Load the name dataset and inspect bigram counts
- Build a `27×27` count matrix `N` (26 letters + start/end token `.`)
- Visualize transition counts with matplotlib
- Sample new names from row-wise probabilities
- Add **Laplace smoothing** (`N + 1`) and resample
- Compute **log-likelihood** and average **negative log-likelihood** (cross-entropy) on the training set
- Build `(xs, ys)` integer tensors for the neural-network bigram model

## Part 2 — neural network bigram (planned)

Same dataset and bigram framing, but the transition table is learned with a small network instead of raw counts.

- [ ] One-hot encode previous character `xs` (27-dim vectors)
- [ ] Linear layer `27 → 27` (no bias, matching the lecture setup)
- [ ] Softmax + **negative log-likelihood** loss on `ys`
- [ ] SGD training loop; track loss vs. the count-based `P` matrix
- [ ] Sample names from the trained weights
- [ ] Compare average NLL to the smoothed count model from Part 1

Progress will land in the same notebook (or a dedicated Part 2 notebook if the file grows too large).

## Project layout

| File | Description |
|------|-------------|
| `bigram_part1.ipynb` | Main notebook (Part 1 complete; Part 2 TBD) |
| `names.txt` | Training names ([Karpathy `makemore`](https://github.com/karpathy/makemore) dataset) |
| `requirements.txt` | Python dependencies |
| `.github/workflows/notebook.yml` | CI: executes the notebook on push/PR |

## Setup

```bash
git clone https://github.com/UShah1996/makemore-bigram.git
cd makemore-bigram

python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

Open `bigram_part1.ipynb` and run all cells from the project root so `names.txt` resolves correctly.

## Requirements

- Python 3.10+
- PyTorch
- matplotlib
- Jupyter

## CI

On every push to `main` (and on pull requests), GitHub Actions runs the notebook end-to-end with a headless matplotlib backend. See the [Actions tab](https://github.com/UShah1996/makemore-bigram/actions).

## Data attribution

`names.txt` comes from the [makemore](https://github.com/karpathy/makemore) repository (US baby names). See that repo for license and provenance.

## References

- [makemore playlist](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhqnK)
- [makemore GitHub](https://github.com/karpathy/makemore)

## License

MIT — see [LICENSE](LICENSE).
