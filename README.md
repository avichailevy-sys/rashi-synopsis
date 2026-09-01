# Rashi Synopsis Viewer — Parashat Lech Lecha

A side-by-side viewer for Rashi's Torah commentary across five manuscript
witnesses and four reference texts, aligned by dibbur hamatchil.

## What it shows

For each of the 206 comments in Parashat Lech Lecha (Genesis 12:1–17:27):

**Reference texts**
- MS Leipzig 1 — the earliest fully transcribed witness; also the row key
- AlHaTorah — eclectic edition based on Leipzig
- Standard text — based on the Reggio/RP"H print
- Rome print — an early print from an independent branch

**Manuscript witnesses** (HTR transcriptions, Kraken 5.3.1)

| Witness | ALMA | Rows aligned (of 206) |
|---|---|---|
| IE21228481 | 990001692110205171 | 168 |
| IE35810661 | 990000829920205171 | 163 |
| IE28267172 | 990001205790205171 | 173 |
| IE58039689 | 990001289260205171 | 140 |
| IE49043068 | 990000852430205171 | 136 |

## How alignment works

Each row is keyed to a dibbur hamatchil from Leipzig 1. That lemma is located
in the manuscript's HTR word stream by fuzzy matching; short lemmas are
additionally verified against the opening words of Leipzig's comment. Candidate
positions across the whole witness are then reduced to the best monotonically
ordered chain, so matches cannot appear out of sequence. Each cell runs from its
lemma to the start of the next located lemma.

## Reading the display

- **ציון** — match confidence for the *lemma only*, 0–100. It says nothing about
  whether the comment agrees with the reference. Below 88 the block is tinted.
- **דף/טור** — folio and column in the manuscript where the segment begins.
- **לא אותר** — not located automatically. This does **not** mean the comment is
  absent from the witness: at current HTR error rates, most non-matches are
  transcription noise.

## Known limitations

- Alignment reaches 136–173 of 206 rows per witness; of those, roughly 80–91%
  contain the correct comment.
- IE35810661 and IE49043068 are unsplit bifolios — two folio-halves per image —
  which the segmentation stage did not separate.
- IE49043068 is filed in the Geniza image store rather than the manuscripts
  store, and covers only Genesis through Leviticus. Its status needs checking.
- Manuscript text is raw HTR output and has not been hand-corrected.

## Structure

```
index.html              viewer
data/lech_lecha.json    aligned text for all witnesses and references
images/                 folio scans (National Library of Israel)
```

To load folios from a remote IIIF service instead of the bundled images, change
`IMAGE_BASE` at the top of the script block in `index.html`.

## Image rights

Folio images are from the National Library of Israel. Check redistribution terms
before publishing this repository publicly.
