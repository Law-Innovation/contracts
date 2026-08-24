# Legal documents

This repository holds Law & Innovation's legal documents. Each product keeps its own
folder. Consenter Manager reads `consenter-manager/` on `main` and publishes those
documents to its customers; no software reads the other folders.

## Layout

```
consenter-manager/<slug>.<locale>.md
```

Every file starts with a frontmatter block:

```yaml
---
slug: tos
locale: en
title: Terms of Use
version: 2026-07
---
```

- `slug` — the document. Same value in every language of that document.
- `locale` — the language. Must match the one in the file name.
- `title` — shown to customers and in the notification email.
- `version` — the revision label, `YYYY-MM` (add a day for a second revision in the same
  month). **This label decides what happens to customers.**

## Changing a document

Edit the files on a branch, keep the frontmatter at the top, and set the `version` label:

- **New label** — a new revision. Every customer is emailed and must agree again.
- **Same label** — a correction. Customers see the new text; nobody is emailed and
  existing agreements stay valid.

Change all languages of a document together, with the same label. Publishing is refused
while one language lags behind.

## Going live

Merging to `main` changes nothing for customers. A document goes live only when someone
with admin rights opens the Legal Documents page in Consenter Manager and clicks Publish.
That screen states, before anything is sent, which documents go out, whether it is a new
revision or a correction, and how many people get an email.

## Adding a document or a language

Add the files, following the same naming and frontmatter — nothing in the software needs
to change. A new document reaches every customer as something to agree to, so treat it
like a new revision. A new language for a revision that is already live is added silently.
