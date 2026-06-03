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

## Part 2 — neural network bigram — done

Same dataset; learn transitions with a `27×27` weight matrix `W` (no bias), one-hot inputs, softmax via `exp` (lecture style), NLL loss + L2 regularization.

- [x] One-hot encode `xs`, forward pass `xenc @ W`
- [x] NLL loss and manual gradient descent
- [x] Full-dataset training loop (100 steps)
- [x] Compare avg NLL to smoothed count matrix `P` from Part 1
- [x] Sample names from trained `W`

See `bigram_part2.ipynb`.

## Project layout

| File | Description |
|------|-------------|
| `bigram_part1.ipynb` | Count-matrix bigram model (Part 1) |
| `bigram_part2.ipynb` | Neural net bigram model (Part 2) |
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

Open `bigram_part1.ipynb` then `bigram_part2.ipynb` from the project root so `names.txt` resolves correctly.

## Requirements

- Python 3.10+
- PyTorch
- matplotlib
- Jupyter

## CI

On every push to `main` (and on pull requests), GitHub Actions runs both notebooks end-to-end with a headless matplotlib backend. See the [Actions tab](https://github.com/UShah1996/makemore-bigram/actions).

## Data attribution

`names.txt` comes from the [makemore](https://github.com/karpathy/makemore) repository (US baby names). See that repo for license and provenance.

## References

- [makemore playlist](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhqnK)
- [makemore GitHub](https://github.com/karpathy/makemore)

## License

MIT — see [LICENSE](LICENSE).
