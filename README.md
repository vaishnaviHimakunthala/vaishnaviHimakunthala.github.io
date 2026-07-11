# Personal Website

Personal site built with [Astro](https://astro.build) — projects, hobbies, and a markdown blog.

## Running locally

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # production build to dist/
```

## Making it yours

- **Intro & hobbies** — edit `src/pages/index.astro` (look for the TODO comments)
- **Projects** — edit the `projects` array in `src/pages/projects.astro`
- **Social links** — edit the footer in `src/layouts/Base.astro`
- **Colors & fonts** — tweak the CSS variables at the top of `src/styles/global.css`

## Writing a blog post

Create a markdown file in `src/blog/`:

```markdown
---
title: My next post
description: A one-line summary.
date: 2026-08-01
tags: [projects]
---

Your content here.
```

Set `draft: true` in the frontmatter to hide a post while you work on it. The
blog index and homepage pick up new posts automatically.

## Contact form

The contact page (`src/pages/contact.astro`) sends messages to your Gmail via
[FormSubmit](https://formsubmit.co) — free, no account required.

**One-time activation:** the first time anyone submits the form, FormSubmit
emails you a confirmation link. Click it once and all future messages are
delivered normally. (Submit a test message yourself after deploying to
trigger this.)

Spam protection: a hidden honeypot field catches bots. If spam becomes a
problem, change `_captcha` to `"true"` in `contact.astro` to add a captcha
step. FormSubmit also gives you a random alias for your address after
activation — swap it into `formEndpoint` if you'd rather not have your email
in the page source (it's currently also in the footer, so remove it there too
if that matters to you).

## Deploying

Live at **https://vaishnavihimakunthala.github.io** via GitHub Pages.

Every push to `main` triggers `.github/workflows/deploy.yml`, which builds the
site and publishes it automatically — no manual steps. Check deploy status
under the repo's Actions tab.

To use a custom domain later, add it in the repo's Settings → Pages and
update `site` in `astro.config.mjs`.
