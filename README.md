# INFOMDSS exam sheet

Double-sided A4 formula & insight sheet for the Data Science and Society (INFOMDSS) exam, written in LaTeX.

## Get the PDF

Every push to `main` builds the sheet automatically:

1. Open the **Actions** tab of this repository.
2. Click the latest **Build exam sheet PDF** run (green check = compiled, red cross = LaTeX error).
3. Download **exam-sheet-pdf** under *Artifacts* (a zip with `main.pdf`).

Print double-sided at **100% / actual size**, not "fit to page".

## File structure

| File | What it does |
|---|---|
| `main.tex` | Page layout only: paper size, orientation, number of columns, order of the topics |
| `style.tex` | Fonts, font size, colours and the entry macros |
| `sections/02`–`11-*.tex` | One file per topic, in course order |
| `sections/12-typical-questions.tex` | Recurring exam question types and how to approach them |
| `.github/workflows/build.yml` | Compiles `main.tex` and uploads the PDF on every push |

## Writing entries

Inside a topic (`\begin{topic}{Title}{colour} ... \end{topic}`):

```latex
\formula{Name}{math}{what it is / how to read the value}   % formula on the same line as its name
\formulaD{Name}{math}{note}                                 % long formula on its own centred line
\insight{Short keyword-style insight}
\ex{Worked example from slides or exercises}
\sub{Small heading}
```

## Common changes

- **Portrait, 3 columns:** in `main.tex` change `landscape` to `portrait` and `\COLS` to `3`.
- **Font size:** in `style.tex` change the `6.5` in `\normalsize` (keep it at 6 or above).
- **Remove a topic:** comment out its `\input{...}` line in `main.tex`.
