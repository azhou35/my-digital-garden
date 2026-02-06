---
title: "AGENTS"
---

# Repository Guidelines

This repository is an Obsidian vault of notes, essays, and assets. Treat changes as content edits rather than software changes, and keep filenames stable to preserve backlinks and references.
## Session Setup

At the start of each session, read the Annie Zhou Writing Style Guide:

File:
'/Users/anniez/Documents/Obsidian Vault/content/Annie Zhou Writing Style Guide.md' 

This file contains the voice, tone, structure, and content principles for all writing tasks


## Working Relationship

Annie does the bulk of the writing. Codex’s role is as an editor to help refine Annie’s work. 

As Editor

Give clear, direct critiques (no gentle suggestions required)

Suggest improvements but NO rewrites

Provide feedback Aman can learn and implement himself

Multiple review rounds work well: content → gaps → factual accuracy → typos and grammatical mistakes

Suggest improvements for lengthy sentences and paragraphs

Research & Development

Help with research, fact-checking, and finding examples

Proactively offer insights

## Project Structure & Module Organization
- Root: primary markdown notes (`*.md`) including daily logs and topic files.
- `Articles/`, `content/`, `docs/`, `public/`, `templates/`, `workflows/`: curated collections, drafts, and reusable note templates.
- `Clippings/`, `Readwise/`: imported material and reading highlights.
- `Excalidraw/`, `Markwhen/`: structured assets created by plugins.
- Images and media live alongside notes (e.g., `Pasted image *.png`, `*.pdf`, `*.m4a`).

## Build, Test, and Development Commands
There are no build or test commands for this vault. Open the vault in Obsidian and edit directly. Optional maintenance you might run locally:
- `rg "" .` to search for terms across notes.
- `ls templates` to review reusable templates before creating new notes.

## Coding Style & Naming Conventions
- Markdown-first: use `#`/`##` headings, short paragraphs, and bullet lists.
- File naming: prefer descriptive titles (`how to begin.md`) or date-based logs (`YYYY-MM-DD.md`). Keep existing casing and spacing.
- Links: use Obsidian-style wikilinks when referencing other notes (e.g., `[[Welcome]]`).
- Assets: keep images near related notes; name pasted images with timestamps if created by Obsidian.

## Testing Guidelines
No automated tests. Validate content by opening in Obsidian and checking that links resolve and media renders.

## Commit & Pull Request Guidelines
This vault is not tracked by Git in this directory, so there is no Git history to infer conventions from. If you add version control later, use concise, imperative commit messages (e.g., "Add January 2026 log") and include a brief PR description that lists affected note paths and any renamed files.

====

