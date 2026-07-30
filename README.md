# ShadowTechLife

Static site for the ShadowTechLife smart-home channel. Built with Astro, deployed on Cloudflare Pages.

## Local development
```
npm install
npm run dev
```
Open http://localhost:4321

## Build
```
npm run build
```
Output goes to `dist/`.

## Adding a guide
Create a new Markdown file in `src/content/guides/`, e.g. `my-new-guide.md`:

```
---
title: "Your title"
description: "One-line summary for search and cards."
category: "Matter & Thread"
date: 2026-08-01
readingTime: "7 min"
draft: false
---

Your content in Markdown.
```

Commit and push — Cloudflare Pages rebuilds automatically. Set `draft: true` to keep one unpublished.

## Deploy settings (Cloudflare Pages)
- Framework preset: Astro
- Build command: `npm run build`
- Build output directory: `dist`

## Newsletter
The signup form on the homepage is a placeholder (`action="#"`). Point it at your email
provider's form endpoint (e.g. Buttondown, MailerLite, Kit) when ready.


