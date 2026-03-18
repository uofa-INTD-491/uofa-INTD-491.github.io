# Add More 2026 Spring Samples Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Expand the `2026 Spring` showcase from 1 sample project to 5 total sample projects.

**Architecture:** Add four new markdown documents under `_projects/` using the existing project front matter contract, plus four matching SVG teaser images under `assets/images/projects/2026-spring/`. Because the site already groups projects by the `semester` field, no layout or navigation changes are required.

**Tech Stack:** Jekyll collections, Markdown front matter, static SVG assets

---

### Task 1: Add four 2026 Spring sample project documents

**Files:**
- Create: `_projects/2026-spring-neighborhood-heat-risk-atlas.md`
- Create: `_projects/2026-spring-makerspace-intake-assistant.md`
- Create: `_projects/2026-spring-transit-access-storyboard.md`
- Create: `_projects/2026-spring-food-rescue-routing-lab.md`

**Step 1: Write the four markdown files**

Use the existing `_projects/_TEMPLATE.md` front matter contract:
- `title`
- `semester: 2026 Spring`
- `team` as a YAML list
- `tags`
- `repo_url`
- `demo_url`
- `poster_image`
- `short_abstract`

Include the standard body sections:
- `Problem`
- `Data`
- `Method`
- `Results`
- `How to run`
- `Links`

**Step 2: Re-read each file**

Check that:
- each file uses a unique slug
- each file points to a matching SVG under `assets/images/projects/2026-spring/`
- at least some projects omit `demo_url` so the conditional button logic remains exercised

### Task 2: Add matching SVG placeholder images

**Files:**
- Create: `assets/images/projects/2026-spring/neighborhood-heat-risk-atlas.svg`
- Create: `assets/images/projects/2026-spring/makerspace-intake-assistant.svg`
- Create: `assets/images/projects/2026-spring/transit-access-storyboard.svg`
- Create: `assets/images/projects/2026-spring/food-rescue-routing-lab.svg`

**Step 1: Add simple SVG poster placeholders**

Each SVG should:
- be static ASCII SVG markup
- include the project title
- match the existing sample poster style closely enough for the showcase

**Step 2: Confirm paths**

Verify each markdown file references the correct SVG path.

### Task 3: Verify content discovery

**Files:**
- Read: `_projects/*.md`
- Read: `assets/images/projects/2026-spring/*.svg`

**Step 1: Count 2026 Spring projects**

Run a search for `semester: 2026 Spring` and confirm there are now 5 project markdown files total.

**Step 2: Check working tree**

Run `git status --short` and confirm the new markdown and SVG files are present.
