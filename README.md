# Personal website — Abin Varghese

A static site (plain HTML/CSS, no build step) with pages for About, Research,
Publications, CV, Teaching, and Blog.

## Before you publish

- Replace the `#` placeholders for **Google Scholar** and **LinkedIn** in the
  sidebar/nav of every page with your real profile URLs (find-and-replace
  `href="#" title="Add your Google Scholar link"` and the LinkedIn
  equivalent works well).
- Swap in a real photo if you'd like one — there currently isn't one, to keep
  things simple; adding an `<img>` to the hero section of `index.html` is the
  natural place.
- `Abin_Varghese_CV.pdf` is your uploaded CV, linked from the CV page.
  Replace this file (keeping the same name, or update the link in `cv.html`)
  whenever you update your CV.
- Add your phone number back to the contact block if you want it public —
  it's currently left off.

## Publishing on GitHub Pages

1. Create a new repository on GitHub. For a site at
   `https://<username>.github.io`, name the repo exactly
   `<username>.github.io`. For a project site at
   `https://<username>.github.io/<repo-name>`, any repo name works.
2. Push these files to the repository root (or to a `docs/` folder if you
   prefer — just set that in step 3):

   ```bash
   cd path/to/this/folder
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo-name>.git
   git push -u origin main
   ```

3. On GitHub, go to the repository's **Settings → Pages**, and under
   "Build and deployment" set the source to "Deploy from a branch", branch
   `main`, folder `/ (root)`. Save.
4. GitHub will publish the site at the URL shown on that Settings page
   (usually within a minute or two).

## Adding a blog post

This is a plain static site, so there's no CMS — a post is just an HTML
file:

1. Duplicate `blog.html`'s `<div class="content">` structure into a new file
   (e.g. `posts/my-first-post.html`), replacing the sidebar links' relative
   paths with `../index.html` etc. since it's one folder deeper.
2. Write your post inside the `.content` div, using `<h1>`, `<p>`, etc.
3. On `blog.html`, replace the empty-state box with an `.entry` block
   linking to the new post — copy the `.entry` pattern used on the
   Research or CV pages.

## Editing the design

All styling lives in `style.css`. The colour palette and type choices are
defined as CSS custom properties at the top of the file, so a rebrand (new
accent colour, different typefaces) is a small, localised edit.
