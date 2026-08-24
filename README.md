# Security Blog — GitHub Pages Setup

## 1. Create the repo

Go to github.com, create a new repo named exactly:

```
your-github-username.github.io
```

(Replace `your-github-username` with your actual username — this exact
naming is what makes it a "user site" served at the root domain instead
of a subpath.)

## 2. Personalize the files

Before pushing, edit:
- `_config.yml` — set `title`, `description`, and your real GitHub/LinkedIn usernames
- `about.md` — fill in your real bio and links
- `index.md` — tweak the intro if you want

## 3. Push it

```bash
cd security-blog
git init
git add .
git commit -m "Initial blog scaffold"
git branch -M main
git remote add origin https://github.com/your-github-username/your-github-username.github.io.git
git push -u origin main
```

## 4. Enable Pages

In the repo on GitHub: **Settings → Pages → Build and deployment → Source:
Deploy from a branch → Branch: main / (root)**. Save. Give it a minute or
two, then your site is live at:

```
https://your-github-username.github.io
```

## 5. Preview locally before pushing (optional but recommended)

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Open http://localhost:4000 to preview before you push.

## 6. Writing new posts

Add a new file to `_posts/` named `YYYY-MM-DD-title-with-dashes.md` with
this front matter at the top:

```yaml
---
layout: post
title: "Your Post Title"
date: 2026-08-23
categories: [web, pentesting]
---
```

Then write in Markdown below it. Commit and push — GitHub Pages rebuilds
automatically within a minute or two.

## Suggested first few posts

1. The Challenge 1 write-up template already included
   (`_posts/2026-08-23-breaking-my-own-llm-app-part-1.md`) — fill it in
   after you complete Challenge 1 in `vulnerable-llm-app`
2. Same treatment for Challenges 2–5
3. A "methodology" post on how you approach a new target (even a lab)
   step by step — hiring managers like seeing process, not just wins
4. Write-ups of your strongest PortSwigger Academy labs
5. Once you have one: your first bug bounty finding (redacted per program
   disclosure rules)
