# jeremysnr.github.io

Personal blog. Jekyll on GitHub Pages, built server-side by GitHub, so there is
no local toolchain to install and nothing to break.

Live at <https://jeremysnr.github.io>

## Writing a new post

Create a file in `_posts/` named `YYYY-MM-DD-some-slug.md`. The date in the
filename is what orders the blog, so it has to be there and has to be in that
format.

```markdown
---
layout: post
title: "Your title here"
date: 2026-08-03 09:00:00 +0100
author: Jeremy Smith
description: >-
  One or two sentences. This is what shows up in Google results and when the
  link is pasted into Slack or LinkedIn.
tags: [ai, policy]
---

Your first paragraph.

## A subheading

More text.
```

Then:

```bash
git add .
git commit -m "New post: your title"
git push
```

GitHub rebuilds the site automatically. It's usually live within a minute.

## Drafts

Put unfinished posts in a `_drafts/` folder with no date in the filename. They
are ignored by the build, so you can commit and push them safely without them
appearing on the site.

## Structure

| Path | What it does |
| --- | --- |
| `_config.yml` | Site title, description, theme, plugins |
| `_posts/` | One Markdown file per published post |
| `assets/main.scss` | Typography overrides on top of the minima theme |
| `about.md` | The About page |
| `index.md` | Homepage, lists all posts automatically |
| `404.html` | Shown for broken links |
| `Gemfile` | Only needed for optional local previews |

## Optional: previewing locally

Not required. GitHub builds the site either way. If you want a local preview you
need Ruby installed, then:

```bash
bundle install
bundle exec jekyll serve
```

and open <http://127.0.0.1:4000>.

## Custom domain

Add a file called `CNAME` at the root containing just your domain, for example
`blog.example.com`, then point a CNAME DNS record at `jeremysnr.github.io`.
Enable "Enforce HTTPS" in the repo's Pages settings once the certificate has
been issued.
