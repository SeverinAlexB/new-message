# Project: Allies of Humanity

This repo contains the full text of the four-book "Allies of Humanity" Briefings plus related Greater Community teachings by Marshall Vian Summers, organized as one directory per book and one markdown file per chapter (front matter, briefings/commentaries, numbered chapters, back matter).

```
book-1-allies-of-humanity/        9 chapter files
book-2-human-unity-and-freedom/   11 chapter files
book-3-a-message-to-earth/        9 chapter files
book-4-freedom-in-the-universe/   8 chapter files
```

It also contains related Greater Community books:

```
greater-community-spirituality-a-new-relevation/ 29 chapter files
wisdom-from-the-greater-community-volume-1/       36 chapter files
```

## Lookup files — use these before scanning source

There is a layered lookup system. Use it rather than blindly grepping all source chapter files:

| File | Purpose |
|---|---|
| **`README.md`** | Human-facing entry point: orientation, links. |
| **`index.md`** (repo root) | Master cross-book index: chapter map for all Allies books plus GCS/WFGC1 + merged A–Z concept index. **Always start here when the user asks where a topic is discussed.** |
| **`book-<N>-*/index.md`, `greater-community-*/index.md`, `wisdom-from-*/index.md`** | Per-book index: chapter title + summary or chapter list + key concepts list when available, then a book-level A–Z concept index where present. |
| **`GLOSSARY.md`** | Definitions of the specialized terminology (Knowledge, Greater Community, Mental Environment, Pacification Program, Collectives, Unseen Ones, etc.) with per-book variations noted. **Look here first when the user asks "what is X?".** |

## Workflow for content questions

1. If the question is "what does <term> mean?" → start in **`GLOSSARY.md`**.
2. If the question is "where does the corpus discuss <topic>?" → start in **`index.md`**, then drill into the relevant per-book `index.md` for chapter summaries.
3. If the question needs a quote or fine detail → read the chapter file itself, citing using the **B`<n>`/`<chapter>`#p`<paragraph>`**, **GCS/`<chapter>`#p`<paragraph>`**, or **WFGC1/`<chapter>`#p`<paragraph>`** form.
4. For verbatim phrase search → `grep -ril "<phrase>" book-*/ greater-community-*/ wisdom-from-*/` against the source files directly. **Do not grep the indexes — they paraphrase or summarize.**

## Citation format

- Books: **B1**, **B2**, **B3**, **B4**, **GCS**, **WFGC1**.
- Chapters: two-digit prefix (e.g. **B2/03** = `book-2-human-unity-and-freedom/03-third-briefing-…md`).
- Paragraphs: appended `#pN` (e.g. **B2/03#p17**) — anchored via inline `<a id="pN"></a>` at each paragraph start.
- The master `index.md` uses the compact form **B`<n>`: <prefix>**, **GCS: <prefix>**, or **WFGC1: <prefix>** (e.g. *B2: 03, 05* or *WFGC1: 03, 14*).

## Notation in the master index

- Chapter refs use the leading two-digit prefix only: e.g. **B2: 03, 05** means *Book 2, files starting with `03-…` and `05-…`*; **WFGC1: 03, 14** means *WFGC1 files starting with `03-…` and `14-…`*.
- Resolve prefixes to full filenames by looking at the chapter map in `index.md` or the per-book index.

## File-level structure (every chapter)

Every chapter `.md` file has this shape:

```markdown
---
book: <book-code>
chapter: "<two-digit-prefix>"
title: "<full title>"
type: front-matter | briefing | commentary | chapter | final-words | back-matter
key_concepts:
  - "..."
  - "..."
---

# <H1 same as title>

<a id="p1"></a>First paragraph...

<a id="p2"></a>Second paragraph...
```

YAML frontmatter is machine-parseable. Paragraph anchors give stable cross-reference points. Headings (`#`, `##`) are NOT anchored — only prose paragraphs.

## Updating things

When chapter files are added, removed, renamed, or substantially edited:

- Update the per-book `index.md` (chapter summary, key concepts, per-book concept index).
- Update the master `index.md` (chapter map and any affected concept refs).
- Update `GLOSSARY.md` only if a specialized term's meaning changes meaningfully.
- Keep the compact **B`<n>`: <prefix>**, **GCS: <prefix>**, and **WFGC1: <prefix>** notation in the master index — don't expand to full filenames.
- Frontmatter: keep `key_concepts` in sync with the per-book index's "Key concepts:" line.
- Paragraph anchors: if you split or merge paragraphs, renumber. The script that originally added them lived at `/tmp/process_chapters.py` (idempotent — safe to re-run).
- Validation: `/tmp/validate_indexes.py` checks per-book index coverage, dead refs in concept entries, and master prefix references.
- **Never include verbatim excerpts in any index or summary file** — summaries should be paraphrased. (Deliberate choice when these were built.)

## Conventions

- Chapter filenames are kebab-case, prefixed with their order (`00-`, `01-`, …). Don't rename without updating both indexes.
- Source markdown uses curly quotes (`"`, `'`) and em-dashes from the original. Don't normalize unless asked.
- Use the books' own terminology when discussing content (Greater Community, Knowledge, Mental Environment, Pacification Program, Collectives, Unseen Ones, Networks of the Wise, Septa Varne, etc.).
