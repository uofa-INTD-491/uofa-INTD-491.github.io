# Contributing a Project

Submit new projects through a pull request.

## Workflow

1. Fork the repository.
2. Create a branch for your project submission.
3. Copy `_projects/_TEMPLATE.md` to a new file such as `_projects/2026-spring-riverwatch-dashboard.md`.
4. Add one image under `assets/images/projects/<semester-slug>/`.
5. Fill in all required front matter fields and the body sections.
6. Change `published: false` to `published: true`, or remove the line entirely.
7. Open a pull request against the default branch.

## Required front matter

- `title`
- `semester`
- `team` as a YAML list
- `tags`
- `repo_url`
- `demo_url`
- `poster_image`
- `short_abstract`

## Image path rules

- Put images under `assets/images/projects/<semester-slug>/`
- Use lowercase filenames with hyphens
- Point `poster_image` at the site-root path, for example:
  - `/assets/images/projects/2026-spring/riverwatch-dashboard.png`

## Semester rules

- The markdown filename can use a slug such as `_projects/2026-spring-riverwatch-dashboard.md`
- The `semester` field should use the display value shown on the site, for example:
  - `2025 Fall`
  - `2026 Spring`
- If you are adding a brand-new semester, copy an existing archive folder such as `2026-spring/` and update:
  - `title`
  - `semester`
  - `semester_order`
  - `description`
  - `permalink`

## Local preview

From the repository root:

```bash
bundle install
bundle exec jekyll serve
```

Then verify:

- your project appears on `/projects/`,
- it appears on the correct semester archive page,
- the poster image loads,
- the repo/demo links work.

The `/projects/` page is the main showcase. Semester archive pages remain available as supporting browse pages.

## Pull request checklist

Before opening a PR, confirm that:

- the markdown file is under `_projects/`
- the image path points into `assets/images/projects/`
- every required front matter field is filled in
- the template `published: false` line has been removed or changed
- links resolve correctly
- the site builds locally
