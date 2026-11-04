---
name: reading-organizer
description: >-
  Organize reading or listening to a professional nonfiction book to optimize
  time, comprehension, retention, and practical implementation. Use when the
  user wants to prepare for a book, plan audiobook listening, identify relevant
  chapters, build a chapter-by-chapter reading guide, set up notes, test recall,
  or turn book insights into scheduled actions.
---

# Reading Organizer

Prepare an objective-driven reading experience, not an exhaustive book summary.
Help the reader extract useful principles, recall them independently, and apply
three to five insights. Support print, digital, and audio formats.

## Input and evidence

Identify the book title, author, edition when relevant, format, available source
material, and any time budget. Reuse information already supplied. Ask only for
missing information that blocks preparation; do not require a lengthy intake.

Use supplied book material first. If browsing or search is available, use it for
the table of contents, publisher or back-cover summary, and two to three reviews,
including at least one critical review when available. Prefer the publisher or
author for bibliographic details and chapter order. Cite consulted sources with
links, distinguish reviewers' opinions from the author's claims, and identify
edition differences that affect the plan.

Established knowledge may support a provisional guide, but is not a substitute
for verified chapter content. State what is missing or uncertain. Never invent
chapter titles, frameworks, quotations, page numbers, timestamps, or review
findings. If search is unavailable or chapter content cannot be established, ask
for a table of contents or relevant excerpts and mark unsupported fields as
pending. Do not imply that a summary or review verifies a full chapter.

## 1. Establish the extraction goal

Do not begin detailed preparation without a clear goal. Use an explicitly stated
goal or ask: "What do you want to learn or do differently after this book?"
If the answer is broad, ask which decision, problem, or behavior it should help.

Write one sentence in the reader's terms:

> I'm reading/listening to this book to learn ...

Examples: run strategic programs with less bureaucracy; influence executives;
understand how AI changes operating models. Use this sentence as the relevance
filter throughout the workflow. Do not silently choose a goal for the user.

## 2. Reconnaissance and time allocation

Review the table of contents, back-cover or publisher summary, and reviews.
Explain the book's overall argument, likely value for the goal, prerequisites,
and important criticisms or limitations. Keep this reconnaissance brief.

Map chapters in published order. Assign each a goal-linked priority:

- **Deep read/listen:** directly useful or needed to understand later chapters.
- **Skim:** supporting context with limited direct relevance.
- **Defer:** low relevance; retain its place in the map for later retrieval.

Give a short reason for each priority. Preserve dependencies even when a chapter
seems less relevant. Do not assume every book has only 20% useful material.
If duration or page counts are known, fit the plan to the reader's time budget;
otherwise use session counts or clearly labeled estimates, not invented timings.

## 3. Prepare the combined notes and guide

Create one Markdown file at `notes/<book-title-slug>.md`, with lowercase,
hyphen-separated words in the slug. If files cannot be written, provide the
template and explain the limitation instead of claiming creation.

Use the current creation date in ISO 8601 form and quote the title safely for
YAML. Start the file with the goal and exactly these three empty capture
sections, in this order; continue with the preparation guide only after them.
Use bullets, not chapter headings, to identify chapters within the capture
sections.

```markdown
---
title: "<Book Title>"
date: YYYY-MM-DD
---

> I'm reading/listening to this book to learn <extraction goal>.

## Ideas

## Actions

## Questions

# Reading Plan

<!-- Continue with the preparation guide here. -->
```

Ideas are useful concepts or principles; Actions are commitments or candidate
experiments; Questions are disagreements, uncertainties, or investigations.
Leave these sections empty at setup rather than preloading answers that would
undermine recall. When updating an existing file, preserve the creation date and
reader's entries; never overwrite them without permission. Keep the notes
placeholder first and the plan after it. Do not create a separate notes file or
competing note archive.

After the capture sections, put the goal, evidence and limitations, priority
map, sequential chapter guide, recall keys, and session checklist in the same
file. Do not link to a separate notes file.

## 4. Build the sequential chapter guide

For each chapter in published order, prepare a concise entry containing:

- **Purpose and fit:** what the chapter contributes to the book and the goal.
- **Main thesis:** the chapter's central claim, in plain language.
- **Frameworks:** relevant models, their use, and their limits; say if none are
  established from the available evidence.
- **Predicted argument:** what the reader expects the chapter to argue and why.
  Label this as a prediction, to be checked after reading.
- **First principles:** distilled statements such as "The key is...", "The
  reason most people fail...", or "Everything comes down to..." where warranted.
  Label paraphrases as synthesis, not author quotations; do not force universal
  claims onto nuanced advice.
- **Application prompt:** one question connecting the chapter to a real decision
  or behavior in the reader's work.
- **Recall test and separate key:** use the procedure below.

For deferred chapters, keep entries brief and mark details pending if necessary.
Do not fill evidence gaps with generic advice dressed as chapter content.
Where only the table of contents is available, provide predictions and questions
first; complete factual theses and keys when reliable material becomes available.

## 5. Read actively and separate stories from principles

Before a chapter, have the reader predict the argument. During it, pause at a
framework, strong claim, disagreement, or useful application. At chapter end,
compare the actual argument with the prediction.

Make notes principle-heavy: roughly 80% principles and applications, at most
20% anecdotes when they clarify a lesson. This is a capture heuristic, not a
claim about every author's writing. Reduce each retained story to the principle
it illustrates; do not reproduce long passages.

Ask of each candidate insight: "Would I spend real money on this advice?"
Keep advice worth testing or changing a decision for, not merely interesting
facts. Aim for one candidate action per relevant chapter, then consolidate to
three to five actions for the whole book. Do not force an action from a chapter
with no useful application.

For audio, recommend low-cognitive-load activities such as walking, train
commuting, familiar exercise, or household chores. Avoid listening while writing
emails, solving problems, building presentations, or participating in meetings.
Pause when reflection needs attention; do not take notes during unsafe activity
such as driving. Adapt session length to the reader's available bandwidth.

## 6. Test recall before revealing answers

At each chapter end and every 30-45 minutes in longer sessions, ask the reader
to answer from memory, without notes or the preparation guide:

1. What were the three main ideas?
2. What surprised me?
3. What will I do differently?

Prepare an answer key per chapter, separately from the questions. In a Markdown
guide, place it in a closed `<details>` block titled "Answer key: open after
recall". In conversation, withhold it until the reader answers or requests it.
Explain that the key is for comparison after recall, not advance memorization.

For question 1, give three source-supported ideas and accept equivalent wording.
If reliable chapter material is unavailable, mark the key pending and request
the relevant material before assessing factual recall.

Questions 2 and 3 are personal, not factual tests. Provide clearly labeled sample
reflections and application options, not invented claims about the reader. A
good surprise identifies a challenged prior belief; a good action identifies a
concrete change, situation, and success signal. Invite "nothing surprised me"
when honest. Compare the reader's answers for accuracy, specificity, and goal
alignment, identify gaps, then revisit only the relevant material and retest.

## Completion check

Before delivering preparation, verify that the goal is explicit, sources and
uncertainties are visible, the priority map and guide preserve chapter order,
and every supported chapter has recall questions and a separate key. Ensure
there is one output file with valid title/date frontmatter, the three empty
capture sections first, and the reading plan after them. Report the actual
output path and next reading session briefly. Distinguish preparation delivered
from recall, delayed review, and implementation still due.