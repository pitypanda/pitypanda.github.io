# Jiacheng Sun — academic website

A small, responsive academic website for https://pitypanda.github.io.
The pages are written in Markdown. GitHub Pages builds them with Jekyll.
You can make every routine update using GitHub's website without installing anything.

## Unpublished draft

The website is stored on the **academic-draft** branch of
`pitypanda/pitypanda.github.io`. This setup does not publish or deploy the
new website. The existing `master` branch and Pages settings are unchanged.

Start here: https://github.com/pitypanda/pitypanda.github.io/tree/academic-draft

When editing on GitHub, keep **academic-draft** selected in the branch menu
and commit your changes to that branch. You can work on the content for as
long as you want. Publishing is a separate step to decide on later.

The original template files are retained. `_config.yml` excludes the old
homepage, archive, demo posts, and old Sass entry points from the new site.
The original version remains on `master` and in Git history.

## What to edit

| File | Purpose |
| --- | --- |
| `index.md` | Home page and biography |
| `research.md` | Research interests, future papers and notes |
| `teaching.md` | Courses, office hours, and public teaching material |
| `cv.md` | Academic background and experience |
| `_config.yml` | Your name, affiliation, public email, and CV PDF path |
| `assets/style.css` | Colors, fonts, spacing, and mobile layout |
| `_layouts/default.html` | Shared navigation and page structure |

To edit a page: open the file on GitHub, click the pencil button, make your
changes, choose **Commit changes**, and commit to `academic-draft`. This saves your edits without deploying the
website. Keep the `---` metadata block at the top
of each page intact. You can change its title, heading, and subtitle.

Your entire website lives in your GitHub account. You can download it, edit
it yourself, or ask any collaborator to work on it later.

## Add your contact information

In `_config.yml`, change the `email` field to your preferred public academic
email, such as `email: "your-address@example.edu"`. The homepage and sidebar
will display it automatically. Your previously public contact email has been retained; change it here if you prefer an academic address.

Review the starter biography and CV before publishing. They contain only
the supplied academic background; paper lists, advisors, awards, and dates
of teaching appointments have not been invented.

## Upload a CV or notes

Upload your PDF into `assets/`. For a CV named `cv.pdf`, change the setting:

```yaml
cv_pdf: "/assets/cv.pdf"
```

For a research note, add this to `research.md`:

```markdown
- [Title of my notes]({{ '/assets/my-notes.pdf' | relative_url }}).
```

## Write mathematics

The layout loads MathJax from a public CDN to typeset LaTeX in the browser.
Use `$...$` for inline mathematics and `$$...$$` for displayed mathematics.
For complicated formulas, a raw HTML wrapper avoids Markdown changing
underscores or backslashes:

```html
<div>
$$
\zeta(s)=\sum_{n=1}^{\infty}\frac{1}{n^s},\qquad \Re(s)>1.
$$
</div>
```

Keep a blank line before and after the wrapper. Math rendering requires an
internet connection to the CDN. The site's text and navigation do not.

## Add another page

Create `notes.md` with:

```yaml
---
title: Notes
heading: Expository notes
section: notes
permalink: /notes/
---
```

Write Markdown below that block, then add a navigation link in
`_layouts/default.html`, following an existing link's pattern.

## Optional local development

With Ruby and Bundler installed, run:

```bash
bundle install
bundle exec jekyll serve
```

Open the local address printed by Jekyll. This is optional; GitHub's web
editor is sufficient for everyday edits. A local preview is only needed
to see the rendered website before publication.

## Official references

- GitHub Pages quickstart: https://docs.github.com/en/pages/quickstart
- Jekyll page editing: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll
- MathJax: https://docs.mathjax.org/en/stable/web/start.html
