# Publish this repo to GitHub

Everything is committed locally on branch `main`. Run these steps once in your terminal.

## 1. Log in to GitHub (one time)

```bash
gh auth login
```

Choose: **GitHub.com** → **HTTPS** → authenticate via browser (recommended).

## 2. Create the remote repo and push

From this folder:

```bash
cd "/Users/urmishah/Library/CloudStorage/OneDrive-Personal/prep-2026/notebooks/Bigram"

gh repo create makemore-bigram --public --source=. --remote=origin --push --description "Part 1: bigram language model from Andrej Karpathy makemore (Jupyter)"
```

Use a different name if you prefer, e.g. `bigram-makemore`.

### Private repo instead

```bash
gh repo create makemore-bigram --private --source=. --remote=origin --push
```

## 3. Verify

```bash
gh repo view --web
```

## Troubleshooting

**`git commit` fails with `unknown option trailer`**

Your global Git alias may wrap `commit`. Use:

```bash
/usr/bin/git commit -m "your message"
```

**No `gh` command**

```bash
brew install gh
```
