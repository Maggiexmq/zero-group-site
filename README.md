# Zero Group website

Website of Zero Group, Division of Decision and Control Systems, KTH.
Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) template.
Every commit to `main` rebuilds the site automatically (see `SETUP_zh.md` for the hosting setup).

## How to update the site

You can do everything in the browser: open a file on GitHub, click the **pencil icon**, edit, then **Commit changes**. The site updates a few minutes later.

| I want to…                         | Edit this                                                                       |
| ---------------------------------- | ------------------------------------------------------------------------------- |
| Change the Home page text          | `_pages/about.md`                                                               |
| Add a news item                    | add a file to `_news/` (see below)                                              |
| Add a paper                        | paste the BibTeX entry into `_bibliography/papers.bib`                          |
| Add, remove or reorder people      | `_data/people.yml`                                                              |
| Add a person's photo               | upload it to `assets/img/people/`, then put the file name in `_data/people.yml` |
| Add a hosted talk                  | `_data/talks.yml`, section `hosted`                                             |
| Add a workshop                     | `_data/talks.yml`, section `workshops`                                          |
| Change Game on! / group meeting    | `_pages/talks.md`                                                               |
| Change open positions              | `_pages/join.md`                                                                |
| Change research areas or projects  | `_pages/research.md`                                                            |
| Change contact address at the bottom | `contact_note` in `_config.yml`                                               |

### Add a news item

On GitHub, open the `_news` folder → **Add file** → **Create new file**. Name it `YYYY-MM-DD-short-name.md`, for example `2026-11-15-new-paper.md`, and paste:

```markdown
---
layout: post
date: 2026-11-15 09:00:00+0100
inline: true
related_posts: false
---

Our paper [Title](https://arxiv.org/abs/xxxx.xxxxx) was accepted at CDC 2026.
```

The Home page shows the 4 newest items; the News page shows all of them.

### Add a person

In `_data/people.yml`, copy an existing block into the right group:

```yaml
- name: Full Name
  url: https://personal-page-or-linkedin
  note: co-advised with Someone
  image: full-name.jpg # optional; leave empty to show initials
```

Photos: square images (e.g. 400×400 px) look best. Upload them to `assets/img/people/`.

### Add a paper

Paste the BibTeX into `_bibliography/papers.bib`. Optional extra fields add buttons: `arxiv = {2404.12165}`, `code = {https://github.com/...}`, `html = {https://publisher-page}`, `doi = {10.1109/...}`.

## Rules for content

- Only write what the group or Giuseppe has stated publicly (website, KTH profile, job ads, news).
- Keep the private phase in mind: while the repository is private, it may later become public together with its full history. Don't commit anything you would not want to be public.

## Preview on your own computer (optional)

With Docker installed: `docker compose up`, then open http://localhost:8080.
Without Docker: install Ruby, then `bundle install` and `bundle exec jekyll serve`, then open http://localhost:4000.

## If the site does not update

Open the Cloudflare dashboard → **Workers & Pages** → the project → **Deployments**, and click the latest deployment to read the build log. The error is usually a typo in a `.yml` file (wrong indentation) or a missing `---` line at the top of a page.
