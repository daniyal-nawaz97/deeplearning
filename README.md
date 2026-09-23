# deeplearning

MIT 6.S191 (Introduction to Deep Learning) labs — PyTorch track.

## Workflow

Edit locally on the laptop, train on Google Colab's GPU.

```
laptop (edit) --> git push --> GitHub --> git pull --> Colab (train on GPU)
```

**Rule: edit notebooks in ONE place only — the laptop.**
Colab pulls and runs. It does not push back. This avoids notebook merge conflicts.

## Layout

| Path | What |
|---|---|
| `lab1/PT_Part1_Intro.ipynb` | Tensors, layers, autodiff. Runs on CPU — do this locally. |
| `lab1/PT_Part2_Music_Generation.ipynb` | Character-level LSTM for music generation. Needs a GPU — run on Colab. |
| `introtodeeplearning/` | MIT's reference clone (gitignored). Holds the solutions and the TF track. |

## Running Part 2 on Colab

1. New Colab notebook -> Runtime -> Change runtime type -> **T4 GPU**
2. Clone this repo:
   ```python
   !git clone https://github.com/daniyal-nawaz97/deeplearning.git
   %cd deeplearning
   ```
   To get later changes: `!git pull`
3. Open `lab1/PT_Part2_Music_Generation.ipynb` from the Colab file browser.
4. The dataset (804 Irish tunes, `irish.abc`) arrives with `pip install mitdeeplearning` —
   nothing to download or commit.

## Comet API key

Part 2 logs training to Comet ML and requires a free API key.
**This repo is public — never type the key into a notebook cell.**
Use Colab Secrets instead (key icon in the left sidebar, name it `COMET_API_KEY`):

```python
from google.colab import userdata
COMET_API_KEY = userdata.get('COMET_API_KEY')
```
