# Reading Machines

A fortnightly reading group website built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

Live at: **https://sonocculture.com/reading-machines/**

---

## Local development

### Prerequisites
- [Hugo extended](https://gohugo.io/installation/) v0.120+
- Git

### First-time setup

```bash
git clone --recurse-submodules https://github.com/sonocculture/reading-machines.git
cd reading-machines
hugo server
```

Then open http://localhost:1313/reading-machines/

> If you cloned without `--recurse-submodules`, run:
> ```bash
> git submodule update --init --recursive
> ```

---

## Adding a new reading

Create a new Markdown file in `content/readings/` named by date:

```bash
hugo new readings/2025-07-13.md
```

Then edit the file's front matter:

```yaml
---
title: "Author — Title of Reading"
date: 2025-07-13
summary: "One-sentence description shown on the list page."
---

**Session N · 13 July 2025**

Full bibliographic details here, plus any notes for the group.
```

Commit and push to `main` — GitHub Actions will build and deploy automatically.

---

## Deployment

The site is deployed via **GitHub Pages** using the workflow in `.github/workflows/deploy.yml`.

### One-time GitHub setup

1. Go to your repo → **Settings → Pages**
2. Under *Source*, select **GitHub Actions**
3. Under **Settings → Actions → General**, ensure *Workflow permissions* is set to **Read and write**
4. Push to `main` — the action will run and publish the site

### Custom domain

In **Settings → Pages → Custom domain**, enter `sonocculture.com` and enable *Enforce HTTPS*.

Add these DNS records at your registrar:

| Type  | Name | Value |
|-------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | sonocculture.github.io |

---

## Light / dark mode

PaperMod follows the visitor's system preference by default (`defaultTheme: auto` in `hugo.yaml`). A toggle button in the top-right corner lets them switch manually.
