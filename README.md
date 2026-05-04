# lizhuoh9.github.io

Personal homepage of **Zhuoheng Li** — PhD Student, Department of Robotics, Hanyang University.

Style: Swiss International Typographic.
Stack: pure HTML + CSS, zero JavaScript, zero build step.

---

## Local preview

Just open `index.html` in any browser, or run a local server (recommended for fonts/anchors):

```bash
# Python 3
python -m http.server 8000

# Node (if you prefer)
npx serve .
```

Then visit `http://localhost:8000`.

---

## Editing content

All content sits in `index.html`. Editable spots are marked with `<!-- EDIT: ... -->`.

| Section       | What to update                                                |
|---------------|---------------------------------------------------------------|
| Profile (Hero)| Name, role lines, and the contact rows (email / Scholar / GitHub / ORCID). Avatar at `assets/avatar.png` |
| About         | Replace the two `<p class="prose">` blocks                    |
| Research      | Edit each `<li class="research-item">` (3 cards by default)   |
| Publications  | Duplicate `<li class="pub-item">` blocks; fill year/venue/title/authors/links. Bold your own name with `<strong>` |

Tip: Bold your name in author lists with `<strong>Zhuoheng Li</strong>`. The CSS underlines it in red automatically.

---

## Adding a profile photo (optional)

Swiss minimalist works without one, but if you want one:

1. Save your photo as `assets/photo.jpg` (square, 800×800 px, < 200 KB).
2. In `index.html` inside the `<section id="about">`, add before the prose:

```html
<img src="assets/photo.jpg" alt="Portrait of Zhuoheng Li"
     width="240" height="240"
     style="margin-bottom: 2rem; filter: grayscale(1);">
```

Grayscale keeps it consistent with the editorial palette.

---

## Deploying to GitHub Pages

**One-time setup:**

1. Make sure your GitHub account `lizhuoh9` has 2FA enabled (Settings → Password and authentication).
2. Create a new **public** repo on GitHub named exactly **`lizhuoh9.github.io`** (this is the magic name for User Pages).
3. Inside this folder, run:

   ```bash
   git init
   git add .
   git commit -m "feat: initial homepage"
   git branch -M main
   git remote add origin https://github.com/lizhuoh9/lizhuoh9.github.io.git
   git push -u origin main
   ```

4. On GitHub: repo → **Settings** → **Pages** → Source: `Deploy from a branch` → Branch: `main` / `/ (root)` → **Save**.
5. Wait 1–2 minutes. Visit **https://lizhuoh9.github.io**.

**Updating the site:**

```bash
git add .
git commit -m "docs: update publications"
git push
```

GitHub Pages rebuilds automatically. New content is live in ~30 seconds.

---

## Custom domain (optional)

If you later buy `zhuohengli.com` or similar:

1. Add a `CNAME` file at the repo root containing only your domain (e.g., `zhuohengli.com`).
2. At your DNS provider, add 4 `A` records pointing the apex to GitHub's IPs:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
3. (Optional) `CNAME` record for `www` → `lizhuoh9.github.io`.
4. In repo Settings → Pages, enter the custom domain and check **Enforce HTTPS**.

---

## Security notes

- The site has **no backend**, **no database**, **no API**. Nothing on the page can be modified by anyone other than the GitHub account holder.
- Keep **2FA on the GitHub account** — that is the only attack surface.
- Optional hardening: turn off Issues / Discussions / Wiki on the repo (Settings → Features), since they are not used.
- Do not commit any secrets, draft papers, or private data into this repo. It is public.

---

## File map

```
.
├── index.html       # Single-page homepage (all sections)
├── styles.css       # Swiss minimalist design system
├── README.md        # This file
├── .nojekyll        # Tells GitHub Pages to skip Jekyll processing
└── assets/          # Your CV, optional photo, etc. (you create)
    └── cv.pdf       # Drop your CV here
```

---

## License of this scaffold

The HTML/CSS scaffold here is yours to modify freely. The personal data on the live site (name, bio, papers, etc.) is © Zhuoheng Li.
