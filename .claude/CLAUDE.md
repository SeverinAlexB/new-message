# Project: Allies of Humanity

This repo contains the full text of the four-book "Allies of Humanity" Briefings by Marshall Vian Summers, organized as one directory per book and one markdown file per chapter (front matter, briefings/commentaries, back matter).

```
book-1-allies-of-humanity/        9 chapter files
book-2-human-unity-and-freedom/   11 chapter files
book-3-a-message-to-earth/        9 chapter files
book-4-freedom-in-the-universe/   8 chapter files
```

## Indexes — read these first when answering content questions

There is an index system you should use rather than scanning all 37 chapter files blindly:

- **`index.md`** (repo root) — master cross-book index. Lists every book, the chapter map for each, and a merged A–Z concept index. **Always start here when the user asks where a topic is discussed.**
- **`book-<N>-*/index.md`** — per-book index. For each chapter: a 2–4 sentence summary in plain language plus a list of key concepts. Also a per-book A–Z concept index.

### Notation used in the master index

- Books are abbreviated **B1**, **B2**, **B3**, **B4**.
- Chapter refs use the leading two-digit prefix: e.g. **B2: 03, 05** means *Book 2, files starting with `03-…` and `05-…`*.
- Resolve prefixes to full filenames by looking at the chapter map in `index.md` or the per-book index.

## Workflow for content questions

When a user asks about a concept, theme, character, or claim from the books:

1. **Look up the concept in `index.md`** to find the candidate book/chapter set.
2. **Open the relevant per-book `index.md`** for the chapter summaries — that's often enough to answer.
3. **Only read full chapter files** when the user wants quotes, fine-grained detail, or the per-book index is not specific enough.
4. **For verbatim phrase search**, use `grep -ril "<phrase>" book-*/` against the source files directly — don't grep the indexes (they paraphrase).

## Updating the indexes

If chapter files are added, removed, renamed, or substantially edited:

- Update the affected per-book `index.md` (chapter summary, key concepts list, per-book concept index).
- Update the master `index.md` (chapter map for that book, and any concept entries that gain/lose chapter refs).
- Keep the **B`<n>`: `<prefix>`** notation consistent — don't switch to full filenames in the master index, it would balloon the file.
- Don't include verbatim excerpts in any index — summaries should be in your own words. (This was a deliberate choice when the indexes were built.)

## Conventions

- Chapter filenames are kebab-case and prefixed with their order (`00-`, `01-`, …). Don't rename them without updating both indexes.
- Source markdown uses curly quotes (`"`, `'`) and em-dashes pulled from the original. Don't normalize unless asked.
- The texts use specialized terminology (Greater Community, Knowledge, Mental Environment, Pacification Program, Collectives, Unseen Ones, Networks of the Wise, Septa Varne, etc.). Use the books' own terms when discussing content.
