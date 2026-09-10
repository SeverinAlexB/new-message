# Project: Allies of Humanity / New Message Corpus

This repo contains a Markdown corpus for *The Allies of Humanity* Briefings and the broader New Message library by Marshall Vian Summers. It includes material from **Volume 0 plus Volumes 1-7** from `newmessage.org`. Chapter text follows the current official web pages, with officially linked PDFs used only where web full text is unavailable.

The corpus is organized as one directory per book or teaching group, with one Markdown file per chapter, lesson, section, or teaching page.

## Main Lookup Files

Use the lookup files before scanning raw source text.

| File | Purpose |
|---|---|
| `README.md` | Human-facing source policy, navigation and citation conventions. |
| `index.md` | Canonical inventory for the four Allies books and New Message Volumes 0-7. Start here for broad navigation. |
| `en/<book-folder>/index.md` | Complete chapter or section list for one book. |
| `GLOSSARY.md` | Source-backed guide to specialized Allies terminology. Start here for term-definition questions. |

## Generated Corpus Scope

The generated New Message folders cover:

- Volume 0: `volume-0-other-teachings/`
- Volume 1: books such as `god-has-spoken-again/`, `the-new-world/`, `the-reformation/`, etc.
- Volume 2: books such as `preparing-for-the-great-waves-of-change/`, `preparing-for-the-greater-community/`, `love-and-relationships/`, etc.
- Volume 3: includes `steps-to-knowledge/`, `steps-to-knowledge-continuation-training/`, `living-the-way-of-knowledge/`, etc.
- Volume 4: includes `greater-community-spirituality/`, `relationships-and-higher-purpose/`, etc.
- Volume 5: includes `life-in-the-universe/`, `the-great-waves-of-change/`, `the-alien-intervention/`, etc.
- Volume 6: `wisdom-from-the-greater-community-book-one/`, `wisdom-from-the-greater-community-book-two/`
- Volume 7: `secrets-of-heaven/`

The four canonical Allies web editions are in `book-1-allies-of-humanity/` through `book-4-freedom-in-the-universe/`.

## Source Policy

Use sources in this order:

- Current official chapter page when it exposes full text.
- Officially linked PDF when the chapter text is not exposed on the web.
- Omit print-only or unavailable content rather than importing unrelated local editions.

`steps-to-knowledge/` is web-sourced. `steps-to-knowledge-continuation-training/` contains only its official web overview. `secrets-of-heaven/` uses its official web introduction and officially linked PDF for the 300 Secrets and related sections.

## Generators

The existing generators were not changed during the source reconciliation and do not reproduce the current corpus exactly. Do not run them against the reconciled Markdown unless the task explicitly includes bringing generator behavior up to date.

| Script | Purpose |
|---|---|
| `tools/generate_newmessage_corpus.py` | Scrapes `https://www.newmessage.org/the-message/`, generates Volume 0-7 web-sourced folders, and updates the generated table in root `index.md`. |
| `tools/generate_pdf_books.py` | Generates Markdown for PDF-backed books and updates root `index.md` counts. |

Typical commands:

```bash
python3 tools/generate_newmessage_corpus.py --root . --force
python3 tools/generate_pdf_books.py
```

Be careful: `--force` deletes and rewrites `*.md` files inside generated book folders. Do not run it if there are intentional manual edits in those folders unless the user approves losing them.

## Workflow For Content Questions

1. For “what does `<term>` mean?” start in `GLOSSARY.md`.
2. For “where is `<topic>` discussed?” start in root `index.md`, then drill into relevant per-book `index.md` files.
3. For exact wording, read chapter/section files and cite file paths plus line numbers or paragraph anchors.
4. For verbatim phrase search, search source Markdown files directly, not just indexes. Indexes may paraphrase.
5. Distinguish explicit text from inference. If a searched term or mechanism is not found, say so directly.

Use `grep`/`rg`-style searches over relevant folders rather than assuming the old Allies-only corpus is complete.

## Citation Format

For broad answers, prefer explicit file references:

- `the-new-world/03-the-global-emergency.md:11`
- `steps-to-knowledge/002-step-1-i-am-without-knowledge-now.md#p1`

Paragraph anchors use inline HTML:

```markdown
<a id="p1"></a>First paragraph...
```

Older curated indexes may use compact abbreviations such as `B1`, `B2`, `GCS`, or `WFGC1`. For the expanded Volume 0-7 corpus, folder paths are usually clearer than introducing new abbreviations.

## File Structure

Generated chapter files generally use this shape:

```markdown
---
volume: 3
book: "Steps To Knowledge"
chapter: "002"
title: "Step 1: I am without Knowledge now."
type: chapter
source_url: "https://..."
source_pdf: "../sources/pdf/..." # only for PDF-derived files
---

# Step 1: I am without Knowledge now.

<a id="p1"></a>First paragraph...
```

Older curated files may instead have frontmatter like `book`, `chapter`, `title`, `type`, and `key_concepts`. Handle both formats.

## Updating Generated Content

When generated corpus files change:

- Update the relevant generator first when possible.
- Rerun the generator.
- Ensure the per-book `index.md` is regenerated.
- Ensure root `index.md` generated table counts are current.
- Do not manually edit generated book files unless the user explicitly wants a one-off correction.

Useful validation checks:

- Every generated chapter/section file should have paragraph anchors.
- Generated files should not contain site chrome such as `Skip to content`, `Toggle Menu`, `Search for:`, `Subscribe and get`, `Scroll to top`, or global sidebar volume trees.
- PDF-derived files should not contain obvious extraction artifacts such as split drop caps (`T here`), stylized headings (`TH E ENG...`), or separator-only paragraphs.

## Conventions

- Preserve the source wording and punctuation unless cleaning obvious extraction artifacts.
- Keep filenames kebab-case and order-prefixed (`00-`, `001-`, `002-`, etc.).
- Use the books' own terminology when discussing content.
- Be precise about whether a claim is explicitly stated, absent from searched text, or an interpretation.


## Languages

The original corpus in English is stored in the `en/` folder. Other translations like `de/` are in their own language folder.
