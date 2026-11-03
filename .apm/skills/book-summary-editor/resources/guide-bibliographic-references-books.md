---
title: Guide to bibliographic references writing: books
author: École polytechnique fédérale de Lausanne
url: https://www.epfl.ch/campus/library/wp-content/uploads/2021/03/Essential_Bibliographic_Versionanglais_20211003.pdf
---

# Bibliographic Citation Guidelines for Books (Agent-Friendly)

## Purpose

A citation must:

1. Attribute ideas, facts, data, quotations, and findings to their original source.
2. Allow a reader to locate the source unambiguously.
3. Prevent plagiarism by clearly distinguishing external content from original work.

---

# Core Principles

## 1. Capture Metadata, Not Just URLs

A URL is only a location.

A citation must primarily identify a resource through its metadata, such as:

- Author(s)
- Title
- Publication date
- Publisher
- Journal or website name
- DOI
- Volume / Issue
- Pages
- Institution

**Rule:** A URL alone is never a sufficient citation.

---

## 2. Prioritize Completeness

The most important rule is:

> A citation is useful only if it contains enough information to uniquely identify the source.

Formatting style is secondary.

A complete citation is more valuable than a perfectly formatted but incomplete citation.

---

## 3. Preserve Accuracy

Metadata must be:

- Correct
- Free of spelling mistakes
- Free of transcription errors
- Taken directly from the source whenever possible

**Rule:** Never invent missing information.

---

# Required Metadata by Source Type

## Book

```yaml
type: book

required:
  - author
  - title
  - publication_date
  - publisher

recommended:
  - place_of_publication
  - edition
  - ISBN
  - DOI
  - URL
  - access_date
```

---

# Citation Quality Rules

## MUST

- Preserve original author names.
- Preserve original titles.
- Include publication date when known.

## SHOULD

- Prefer DOI over URL.
- Record edition for books.
- Record identifiers such as:
  - DOI
  - ISBN
  - ISSN

## MUST NOT

- Use only a URL as a citation.
- Omit known authors.
- Omit known publication dates.
- Fabricate metadata.
- Replace bibliographic metadata with hyperlinks.

---

# Agent Citation Workflow

```yaml
citation_workflow:

  - identify_source_type:
      - book
      - chapter
      - journal_article
      - thesis
      - dataset
      - encyclopedia_article
      - web_page
      - video

  - collect_required_metadata

  - collect_recommended_metadata

  - determine_best_identifier:
      priority:
        - doi
        - repository_identifier
        - permalink
        - url

  - add_access_date_if_online

  - validate_completeness

  - validate_accuracy

  - render_in_requested_style:
      - IEEE
```

---

# Minimal Metadata Contract for Agents

```yaml
citation:

  type: <source_type>

  title: required

  author:
    required_when_known: true

  publication_date:
    required_when_known: true

  identifier:
    preferred:
      - DOI
      - ISBN
      - ISSN

  location:
    - URL

  access_date:
    required_for_online_resources: true
```

---

# Golden Rule

> The purpose of a citation is not stylistic perfection. The purpose is to provide complete, accurate, and verifiable metadata that allows a reader to identify, locate, and retrieve the source without ambiguity.