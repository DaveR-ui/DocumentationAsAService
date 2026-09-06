---
id: new-note-checklist
category: Checklists
tags:
- checklist
- contract
aliases:
- New Note Checklist
related:
- document-template
version: 1.3
status: active
---

# New-Note Checklist

## Problem

The contract has ~20 individual requirements; "I'll remember them all" fails silently at exactly
the moment nobody checks.

## Solution

Run this list before declaring a new note done — this list *is* the check. Every item is
objective enough to automate someday; today, the walking is the point.

**Metadata**
- [ ] All 7 required keys present: `id`, `category`, `tags`, `aliases`, `related`, `version`, `status`.
- [ ] `id` is a slug, unique corpus-wide, ≈ filename stem + category.
- [ ] `status` ∈ {`draft`, `active`, `superseded`, `expired`} (`archived` notes live outside the served root).
- [ ] Optional keys (`supersedes`, `expires_at`) either valid or *entirely absent* — never blank.

**Body**
- [ ] H1 title present (`no H1 title` warning), then the 7 sections verbatim and in order.
- [ ] "When not to use" and "Common mistakes" are real, not "N/A" filler.
- [ ] Language matches the corpus `doc_language`.

**Graph**
- [ ] Every `related` id resolves (the dangling-related-target check).
- [ ] Every `[[wikilink]]` stem/alias resolves (the dangling-link check).
- [ ] Note has ≥1 resolved non-self edge (the orphan-note check) — otherwise it is an island.
- [ ] Note is listed in its folder's hub via wikilink or markdown link (missing from its hub).

**Hygiene**
- [ ] No secret-like tokens in prose or frontmatter (secret in prose); don't put secrets in the corpus at all.
- [ ] The generated index region of `index.md` lists the note (the stale-index check); follow every link in the note once — a dead end is a finding.

## When to use

Every note creation or major edit, before the merge.

## When not to use

Repo-level docs under the lighter context-doc contract (frontmatter `last_updated`, `status`,
`description`, `tags`) — still check links and language.

## Examples

Compare a just-written note against the micro-vault in [`../guidelines/09-bootstrap-workflow.md`](../guidelines/09-bootstrap-workflow.md) — its frontmatter and link wiring satisfy every box (bodies are abbreviated for space; the section skeleton is the template's job).

## Common mistakes

- Checking the boxes by editing the checklist instead of the note.
- Adding `related` targets "that sound right" without verifying resolution — the next reviewer
  will, now or later.

## References

- [../Templates/document-template.md](../Templates/document-template.md) — the contract itself.
- [../guidelines/04-validation.md](../guidelines/04-validation.md) — the review catalog this mirrors.
