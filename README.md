# The Allies of Humanity — Corpus

Full text of the four-book *Allies of Humanity* Briefings by Marshall Vian Summers (1996–2016), organized for fast lookup by humans and AI tools alike.

## What is this?

A series of "Briefings" framed as transmissions from a covert multi-racial extraterrestrial expedition (the Allies) sent to warn humanity about an ongoing alien Intervention seeking Earth's resources and allegiance through persuasion rather than force. The Briefings introduce a self-contained vocabulary — Greater Community, Knowledge, Mental Environment, Pacification Program, Collectives, Unseen Ones, Networks of the Wise — used consistently across the four books.

## Books

| | Title | Year | Files | Open |
|---|---|---|---|---|
| **B1** | The Allies of Humanity | 2001 | 9 | [`book-1-allies-of-humanity/`](book-1-allies-of-humanity/index.md) |
| **B2** | Book Two — Human Unity & Freedom | 2005 | 11 | [`book-2-human-unity-and-freedom/`](book-2-human-unity-and-freedom/index.md) |
| **B3** | Book Three — A Message to Earth | 2008 | 9 | [`book-3-a-message-to-earth/`](book-3-a-message-to-earth/index.md) |
| **B4** | Book Four — Freedom in the Universe | 2016 | 8 | [`book-4-freedom-in-the-universe/`](book-4-freedom-in-the-universe/index.md) |

Each book is one directory; each chapter is one markdown file (`00-front-matter.md`, `01-first-briefing-…`, …, back-matter).

## Where to start

| If you want to… | Go to |
|---|---|
| Find which chapter discusses a topic | [`index.md`](index.md) — master cross-book concept index |
| Read a chapter summary | per-book `index.md` (linked above) |
| Look up a specialized term | [`GLOSSARY.md`](GLOSSARY.md) |
| Read the source text | the chapter `.md` files in each book directory |

## Citation format

- Books: **B1**, **B2**, **B3**, **B4**.
- Chapters: two-digit prefix (e.g. **B2/03** = Book 2's `03-third-briefing-…md`).
- Paragraphs: appended `#pN` (e.g. **B2/03#p17**) — anchored via `<a id="pN"></a>` at each paragraph start.

## File-level conventions

- Every chapter file begins with YAML frontmatter: `book`, `chapter`, `title`, `type`, `key_concepts`. The H1 follows.
- Paragraph anchors (`<a id="pN"></a>`) precede each paragraph for stable cross-references.
- Source punctuation (curly quotes, em-dashes) is preserved as-published.

## Working with the corpus

Direct grep against the source is the fastest path for verbatim phrase search:

```bash
grep -ril "Pacification Program" book-*/        # any book
grep -in  "hybrid"                book-2-*/*.md # one book, with line numbers
grep -l   "Septa Varne"           book-*/*.md   # which chapters mention it
```

For concept-level lookup ("which chapters discuss X?"), open [`index.md`](index.md) first, then drill into the per-book index for chapter summaries before reading source.

## For AI agents

See [`CLAUDE.md`](CLAUDE.md) for the recommended workflow and conventions when answering questions about this corpus.
