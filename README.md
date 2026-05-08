# Mattiazzi Lab Website

Jekyll-based GitHub Pages site for the Mattiazzi Lab.

## Local development

```bash
bundle install
bundle exec jekyll serve
# Open http://localhost:4000
```

## How to edit content

| What to update | File to edit |
|---|---|
| Site title, email, address | `_config.yml` |
| Team members | `_data/team.yml` |
| Publications | `_data/publications.yml` |
| News & announcements | `_data/news.yml` |
| Research page text | `research.md` |
| Contact page | `contact.md` |
| Navigation links | `_config.yml` → `nav_links` |

## Adding a team photo

1. Drop the image file into `assets/images/team/`
2. In `_data/team.yml`, set `image: team/filename.jpg`

## Deploying to GitHub Pages

1. Push this repo to GitHub
2. Go to Settings → Pages
3. Set Source to **Deploy from a branch**, branch `main`, folder `/`
4. The site will build automatically on every push
