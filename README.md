# Tanakit Jansom — personal site

Two files, one folder, no subfolders and no build step:

- `index.html` — the content
- `style.css` — the styling

There is no JavaScript. Colours are carried over from the original Ronin template
(violet `#8490ff` → sky `#62bdfc`, Heebo/Roboto type). Open `index.html` in a browser
to preview — what you see locally is what GitHub Pages serves.

The one external request is the Google Fonts link in the `<head>`. Delete that line if
you want zero dependencies; the page falls back to your system font and still works.

## Publishing to `<username>.github.io`

1. Create a GitHub repo named **`<your-username>.github.io`** — that exact name is what
   makes the URL work.
2. Push this folder to `main`:

   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-username>.github.io.git
   git push -u origin main
   ```

3. Repo **Settings → Pages** → source `main` / `/ (root)`.
4. Visit `https://<your-username>.github.io`.

Every later `git push` redeploys.

## Filling it in

All placeholders are in `index.html`, marked with comments:

| What | Where |
|---|---|
| Bio paragraph | `hero__bio` — the `[your research area]` bits |
| Email | the `mailto:you@vistec.ac.th` link |
| Scholar / GitHub / LinkedIn | the `href="#"` links in `<ul class="socials">` |
| Research themes | the three `<article class="card">` blocks |
| Publications | the `<li class="pub">` blocks, newest first |

To change the accent colour, edit `--base` and `--sky` at the top of `style.css`.
Buttons, the hero, and the year badges all derive from those two values.

## Adding your photo

Save a square photo as `profile.jpg` in this folder, then in `index.html` swap which of
these two lines is commented out:

```html
<!-- <img class="photo" src="profile.jpg" alt="Tanakit Jansom"> -->
<div class="photo photo--empty">profile.jpg<br>goes here</div>
```

Other pictures go in this same folder, referenced by filename. Keep them under ~500 KB.

## Adding your CV

Drop `cv.pdf` in this folder — the "Download CV" button already points at it.
