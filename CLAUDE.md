# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This is the main index/landing page for the **TEA/Branch** GitHub organization (`teabranch`). It serves as a central hub pointing to the org's other repositories and projects.

## Repository State

This repository contains a custom Jekyll site for the organization's landing page, deployed to `teabranch.dev` via GitHub Pages. It uses Ruby/Bundler (`Gemfile`), Jekyll configuration (`_config.yml`), custom layouts (`_layouts/`), includes (`_includes/`), and a hand-crafted CSS stylesheet (`assets/css/style.css`). Build and deploy via `bundle install && bundle exec jekyll serve` locally, or GitHub Actions for production.

## Build Commands

```bash
bundle install              # Install Ruby dependencies
bundle exec jekyll serve    # Serve locally at localhost:4000
bundle exec jekyll build    # Build to _site/
```

## License

MIT — Copyright (c) 2026 TEA/Branch
