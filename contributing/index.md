---
title: Contributing
permalink: /contributing/
layout: default
---
# Contributing a Project

Submit new projects through a pull request.

## Workflow

1. Fork the repository.
2. Create a branch for your submission.
3. Copy `_projects/_TEMPLATE.md` to a new file in `_projects/`.
4. Add one poster or teaser image under `assets/images/projects/<semester-slug>/`.
5. Fill in the required front matter and body sections.
6. Change `published: false` to `published: true`, or remove the line entirely.
7. Open a pull request to the default branch.

## Required fields

- `title`
- `semester`
- `team`
- `tags`
- `repo_url`
- `demo_url`
- `poster_image`
- `short_abstract`

## Image path example

- `/assets/images/projects/2026-spring/riverwatch-dashboard.png`

## Semester values

- `2025 Fall`
- `2026 Spring`

If you need a new semester archive, copy an existing folder like `2026-spring/` and update its front matter before adding projects for that term.

## Preview locally

From the repo root:

```bash
bundle install
bundle exec jekyll serve
```

Then open the local address shown in the terminal and verify:

- your project appears on `/projects/`,
- it appears on the correct semester archive page,
- the poster image loads,
- the repo/demo links work.
