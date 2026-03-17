# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal academic website for John Seon Keun Yi, hosted on GitHub Pages. It is a static site with no build system — changes to `index.html` and `stylesheet.css` are deployed directly by pushing to the `master` branch.

## Structure

- `index.html` — Single-page site containing all content: bio, research papers, projects, and misc sections
- `stylesheet.css` — All site styles, including custom element tags (`<name>`, `<heading>`, `<papertitle>`)
- `images/` — Paper thumbnail images; hover-swap pairs follow the naming convention `{key}_before.*` and `{key}_after.*`
- `data/` — Static files (e.g., CV PDF)

## Content Patterns

**Research/project entries** in `index.html` follow a consistent `<tr>` structure:
1. Left cell (25% width): thumbnail image, optionally with a hover-swap effect using `.one`/`.two` CSS classes and inline JS functions named `{key}_start()` / `{key}_stop()`
2. Right cell (75% width): `<papertitle>`, authors (`<strong>` for self), venue in `<em>`, links, and a short description

**Hover image swap** pattern — each interactive thumbnail needs:
- A wrapping `<div class="one">` containing an inner `<div class="two" id='{key}_image'>` (the "after" image) over the base image
- Inline `<script>` with `{key}_start()` / `{key}_stop()` toggling opacity
- `onmouseover` / `onmouseout` on the parent `<tr>`

## Deployment

Push to `master` — GitHub Pages serves the site automatically. There is no build step, linter, or test suite.
