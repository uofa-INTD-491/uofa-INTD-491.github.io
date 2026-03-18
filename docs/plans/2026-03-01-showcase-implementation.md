# INTD 491 Showcase Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Build a complete GitHub Pages-ready Jekyll showcase repo for INTD 491 projects.

**Architecture:** Use a `_projects` collection for detail pages, normal pages for semester archives, and custom layouts/includes on top of Minimal Mistakes. Deployment injects repository-aware `url` and `baseurl` values during the Pages build.

**Tech Stack:** Jekyll 4, Minimal Mistakes, GitHub Actions, Liquid templates, Sass

---

### Task 1: Create the Jekyll foundation

**Files:**
- Create: `_config.yml`
- Create: `Gemfile`
- Create: `.gitignore`
- Create: `_data/navigation.yml`

**Step 1:** Define the site config, theme, collection, plugins, and page defaults.

**Step 2:** Add Gem dependencies for Jekyll, Minimal Mistakes, and `jekyll-include-cache`.

**Step 3:** Add navigation and local build ignores.

### Task 2: Build the rendering layer

**Files:**
- Create: `_includes/semester-label.html`
- Create: `_includes/project-card.html`
- Create: `_layouts/projects_home.html`
- Create: `_layouts/semester_archive.html`
- Create: `_layouts/project.html`
- Create: `assets/css/main.scss`

**Step 1:** Build reusable Liquid includes for semester labels and project cards.

**Step 2:** Create the home, archive, and project layouts.

**Step 3:** Add custom styling for card grids and project detail panels.

### Task 3: Seed the content model

**Files:**
- Create: `index.md`
- Create: `2025-fall/index.md`
- Create: `2026-spring/index.md`
- Create: `_projects/_TEMPLATE.md`
- Create: `_projects/*.md`
- Create: `assets/images/posters/*.svg`

**Step 1:** Add two semester archive pages.

**Step 2:** Add sample projects that exercise every required front matter field.

**Step 3:** Add sample poster assets and a reusable project template.

### Task 4: Document authoring and deployment

**Files:**
- Create: `README.md`
- Create: `CONTRIBUTING.md`
- Create: `.github/workflows/pages.yml`

**Step 1:** Document local development and content authoring.

**Step 2:** Add the Pages deployment workflow with runtime `url`/`baseurl` detection.

### Task 5: Verify the scaffold

**Files:**
- Generate: `Gemfile.lock`

**Step 1:** Run `bundle install`.

**Step 2:** Run `bundle exec jekyll build`.

**Step 3:** Fix any Liquid, theme, or asset issues until the build succeeds.

