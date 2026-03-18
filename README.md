# INTD 491 Project Showcase

A Slate-themed GitHub Pages site for publishing student projects as a semester-grouped showcase with individual project detail pages.

## Local development

Install dependencies:

```bash
bundle install
```

Serve the site locally:

```bash
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000/`.

## Where content lives

- `_projects/` contains one markdown file per student project.
- `projects.md` is the canonical project index at `/projects/`.
- `2025-fall/index.md` and `2026-spring/index.md` are semester archive pages.
- `assets/images/projects/<semester-slug>/` stores teaser or poster images used on cards and detail pages.

## Project front matter

Each project file must define:

- `title`
- `semester`
- `team` as a YAML list
- `tags`
- `repo_url`
- `demo_url`
- `poster_image`
- `short_abstract`

Use `_projects/_TEMPLATE.md` as the starting point.

## Add a new semester

1. Copy an existing folder such as `2026-spring/`.
2. Rename it to the new slug, for example `2026-fall/`.
3. Update the front matter in `index.md`:
   - `title`
   - `semester`
   - `semester_order`
   - `description`
   - `permalink`
4. Add projects under `_projects/` using the matching display value in `semester`, for example `2026 Fall`.

## Add a new project

1. Copy `_projects/_TEMPLATE.md` to a new file.
2. Add your image under `assets/images/projects/<semester-slug>/`.
3. Fill in the front matter and body content.
4. Remove `published: false` or change it to `published: true`.
5. Confirm it appears on `/projects/` and on the matching semester archive page.

See `CONTRIBUTING.md` for the student-friendly version.

## Semester display behavior

- `/projects/` groups projects by the `semester` field and shows the showcase in a fixed two-column grid on desktop.
- Sections are ordered by the archive pages' `semester_order` values, newest first.
- Semester archive pages stay available at stable URLs such as `/2026-spring/`.

## Baseurl note

This repository is configured as a GitHub Pages project site. Keep the `_config.yml` `url` and `baseurl` values intact so that all `relative_url` links and images resolve correctly at `https://jeremykid.github.io/intd491-projects/`.
