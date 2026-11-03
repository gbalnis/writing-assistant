---
name: book-summary-editor
description: >-
  Create a structured summary of a professional software-development book — covering software engineering practice, development organization/process, or the psychology of the work — with key points to remember and guidance on when and for what purpose to return to the book. Use when the user asks to summarize a book or distill its main ideas.
---

# Book Summary

Produce a reference-quality summary of a professional book about software
development: engineering practice, organization of development work,
process/methodology, or the psychological and human complexity of the work.

The summary serves two goals:

1. **Retention** — the main points worth remembering without re-reading.
2. **Retrieval** — knowing exactly when and why to come back to the book.

## Input handling

Identify what source material is available, in this order:

1. The user provides text, a file, or excerpts of the book → summarize from
   that material only.
2. The book is a well-known professional title (e.g. *The Pragmatic
   Programmer*, *Peopleware*, *The Mythical Man-Month*, *Accelerate*, *Clean
   Architecture*) → summarize from established knowledge of the book.
3. The book is obscure or unfamiliar → say so honestly, then ask the user for
   excerpts, a table of contents, or notes. **Never fabricate** chapter
   contents, quotes, or page numbers.

Ask at most one round of clarifying questions if the edition or scope
(whole book vs. specific chapters) is unclear.

## Output structure

Always write the summary to a Markdown file at
`content/book-club/<slug-of-title>.md` (create the directory if needed), e.g.
`content/book-club/the-mythical-man-month.md`. Never return the summary only
in chat — after writing the file, reply with its path and a 2–3 sentence
teaser of the core thesis. If the same book is summarized again, overwrite
the existing file. Preface content with Hugo front matter.

Use this skeleton, adapting section names to the book type (engineering / organizational / psychological):

```markdown
---
title: "<Book Title>"
date: <Date when this document is created in ISO 8601 format>
markup: markdown
draft: true
summary: <1-2 sentences describing the essence of the book: what it argues and why it matters>
keywords: <add relevant keywords based on the book's content in a human-readable format, no kebab-case!>
params:
  author: <User's Name>
---

> Formal citation of the book, use the rulebook for bibliographic references in `<skill-dir>/resources/guide-bibliographic-references-books.md`.

## Metadata

- **Type**: engineering practice / organization & process / psychology & people
- **Reading effort**: short / medium / long
- **Prerequisites**: experience or knowledge that makes the book land
- **Summary based on**: full text / reader's notes / excerpts / general knowledge

## Quick summary

1-2 sentences describing the essence of the book: what it argues and why it matters.

## Core thesis

2–4 sentences: the central claim of the book and the problem it answers.

## Key points to remember

The heart of the summary. 7–15 numbered points, each:

1. **<Memorable name or principle>** — one crisp statement of the idea,
   then 1–3 sentences of explanation: why it holds, what it contradicts,
   and what it looks like in practice. Include a vivid example, rule of
   thumb, or aphorism from the book when one exists.

Order points from most to least fundamental. Every point must be
actionable or perspective-shifting — cut pure trivia.

## Mental models and frameworks

Named models, laws, diagrams-in-words, or classification schemes from the
book (e.g. "Conway's Law", "Four key metrics", "Brooks's Law"). For each:
what it is, when it applies, when it breaks.

## When to return to this book

A lookup table — the second goal of the summary. Map concrete professional
situations to the chapters or ideas to revisit:

| Situation you face | Return for |
| --- | --- |
| e.g. Team slows down as it grows; adding people makes it worse | Chapter on communication overhead — re-read the argument and the numbers |
| e.g. Arguing with management about estimates | The chapters on estimation fallacy and schedule pressure |

Cover at least: crisis situations, decision dilemmas, recurring team
dysfunctions, career moments, and situations where the book's advice is
controversial or counterintuitive.

## Limitations and context

- When and where the book was written, and what may be dated (tools,
  org shapes, market conditions).
- Main criticisms or schools of thought that disagree.
- What the book deliberately ignores.

## Companion reading

2–4 books that extend, update, or contradict this one, with a phrase on
why each pairs with it.
```

## Quality bar

- **Fidelity over coverage.** Better to capture the 10 ideas that carry the
  book than to flatten it into 30 generic bullets.
- **Preserve the author's voice** where it matters — distinctive terms,
  laws, and aphorisms aid memory. Attribute them; do not invent quotes.
- **Points must survive context collapse.** A point re-read in a year,
  without the conversation around it, must still make sense standalone.
- **Situations in the return-table must be recognizable.** Write them as
  the reader would describe their own problem ("being pushed to commit to
  a deadline on a project that's already late"), not as abstract topics.
- **No padding.** If a section adds nothing for a given book, drop it and
  say why in one line.
- Keep the whole summary readable in under 10 minutes; the book is the
  long version, the summary is the index into it.
