---
title: Guide to bibliographic references writing
author: École polytechnique fédérale de Lausanne
url: https://www.epfl.ch/campus/library/wp-content/uploads/2021/03/Essential_Bibliographic_Versionanglais_20211003.pdf
---

# Bibliographic Citation Guidelines (Agent-Friendly)

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

## 4. Prefer Persistent Identifiers

Use the following order of preference:

1. DOI
2. Stable repository identifier
3. Permanent URL
4. Ordinary URL

DOIs are preferred because they remain stable even when locations change.

---

## 5. Record Access Information for Online Resources

For online content include:

- DOI or URL
- Access date

For mutable resources (Wikipedia, collaborative knowledge bases, social media, etc.), use a permalink or revision-specific URL when available.

---

# In-Text Citations

The guide identifies four major citation families:

| Style | Example |
|---------|---------|
| Author-Date | (Smith, 2024) |
| Numeric | [12] |
| Note-Based | Footnote reference |
| Label-Based | [Smi24] |

The citation style determines presentation only. The required metadata remains the same.

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

## Book Chapter

```yaml
type: book_chapter

required:
  - chapter_title
  - chapter_author
  - book_title
  - book_editor_or_author
  - publication_date
  - page_range
  - publisher

recommended:
  - place_of_publication
  - ISBN
  - DOI
  - URL
  - access_date
```

---

## Journal Article

```yaml
type: journal_article

required:
  - article_title
  - author
  - journal_title
  - publication_date
  - volume

recommended:
  - issue
  - page_range
  - DOI
  - URL
  - access_date
  - ISSN
```

Notes:

- Always include the journal title.
- Include DOI whenever available.

---

## Thesis / Dissertation

```yaml
type: thesis

required:
  - title
  - author
  - thesis_type
  - institution
  - publication_date

recommended:
  - place
  - supervisor
  - DOI
  - URL
  - access_date
```

---

## Research Dataset

```yaml
type: dataset

required:
  - title
  - creator
  - publication_date
  - repository

recommended:
  - DOI
  - URL
  - access_date
  - license
```

Notes:

- Treat datasets as independent scholarly outputs.
- Cite the dataset itself, not only the associated paper.

---

## Encyclopedia Article

```yaml
type: encyclopedia_article

required:
  - article_title
  - encyclopedia_name

recommended:
  - author
  - publication_date
  - volume
  - URL
  - access_date
```

Rule:

- Include the author whenever one is identified.

---

## Web Page

```yaml
type: web_page

required:
  - page_title
  - website_name

recommended:
  - author
  - last_update_date
  - URL
  - access_date
```

Notes:

- Tweets, social media posts, and Facebook pages can generally be treated as web pages.

---

## Video

```yaml
type: video

required:
  - title
  - creator
  - publication_date

recommended:
  - duration
  - studio_or_platform
  - location
  - URL
  - access_date
```

---

# Citation Quality Rules

## MUST

- Preserve original author names.
- Preserve original titles.
- Include publication date when known.
- Include source container (journal, book, repository, website).
- Include DOI when available.
- Include access date for online resources.
- Cite the exact source consulted.
- Provide enough metadata to uniquely identify the source.

## SHOULD

- Prefer DOI over URL.
- Record edition for books.
- Record page ranges.
- Capture repository names for datasets.
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
      - APA
      - Chicago
      - IEEE
      - Vancouver
      - Harvard
      - Numeric
      - AuthorDate
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

  container:
    description: journal, book, repository, website, institution
    required_when_applicable: true

  identifier:
    preferred:
      - DOI
      - ISBN
      - ISSN
      - Repository ID

  location:
    - URL

  access_date:
    required_for_online_resources: true
```

---

# Golden Rule

> The purpose of a citation is not stylistic perfection. The purpose is to provide complete, accurate, and verifiable metadata that allows a reader to identify, locate, and retrieve the source without ambiguity.