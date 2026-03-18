# INTD 491 Showcase Design

## Goal

Create a GitHub Pages-ready Jekyll repository that showcases student projects by semester, using a lightweight authoring model and no unsupported runtime tricks.

## Design decisions

- Use `minimal-mistakes-jekyll` for a maintained theme with solid layout primitives and easy override points.
- Model student work as a Jekyll collection under `_projects/`, with one markdown file per project.
- Model semester archives as normal pages with a shared `semester_archive` layout. This avoids unsupported page-generation plugins while still producing clean URLs like `/2026-spring/`.
- Build the home page from semester archive pages so the landing page and archive ordering stay explicit.
- Use `relative_url` everywhere and patch `url` / `baseurl` in the GitHub Actions workflow so the same repo deploys cleanly as either a user site or project site.

## Content flow

1. Students add one image under `assets/images/posters/`.
2. Students copy `_projects/_TEMPLATE.md` to a new file and fill in front matter.
3. Instructors or TAs add a new semester by copying an existing `YYYY-term/index.md` page and updating the front matter.

## Constraints handled

- No unsupported page-generator plugins.
- Local development works with `bundle install` and `bundle exec jekyll serve`.
- GitHub Actions installs all required gems and deploys to Pages.

