# adityaagrawal.dev

Personal website / research portfolio. Plain HTML + CSS, no build step.

## Local preview

```bash
# Pick any one
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a public repo on GitHub named **`1310aditya.github.io`** (the
   repo name must match your GitHub username for a user/organization site).
2. From this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin git@github.com:1310aditya/1310aditya.github.io.git
   git push -u origin main
   ```
3. In the repo's **Settings → Pages**, source = **Deploy from a branch**,
   branch = **main**, folder = **/ (root)**. Save.
4. The site will be live at `https://1310aditya.github.io` within a minute
   or two.

### Custom domain (optional)

1. Buy a domain (Namecheap, Cloudflare Registrar, etc.).
2. At the registrar, add these DNS records pointing to GitHub Pages:
   - `A` records for the apex (`@`) → `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - `CNAME` for `www` → `1310aditya.github.io`
3. Add a `CNAME` file at the root of this repo containing just your domain
   (e.g. `adityaagrawal.dev`).
4. In GitHub Pages settings, set the custom domain and enable **Enforce
   HTTPS** once the cert provisions.

## Adding content

### Avatar

Drop a square photo at `assets/avatar.jpg`. It auto-hides if missing.

### Art

1. Add image files to `assets/art/`.
2. In `index.html`, inside the `<div class="gallery">`, add one `<figure>`
   per image — there's a commented-out template already there.

### Publications

In `index.html`, copy any `<li class="pub">` block in the publications
list and edit it. Keep the `pub-meta`, `pub-title`, `pub-authors`,
`pub-abstract` structure.

### Internal Amazon papers — content guardrails

When writing about internal work, **do not include**:
- internal product/codenames
- proprietary dataset names, sizes, or schemas
- specific implementation details that could constitute IP leakage
- non-public roadmap or strategy

Revenue/business numbers that have been disclosed elsewhere (e.g. on the
public resume) are okay to keep at this level of generality.

## Files

```
.
├── index.html      # the whole site
├── styles.css      # tokens + light/dark theme
├── assets/
│   ├── avatar.jpg  # optional, drop in to enable
│   └── art/        # gallery images
├── .gitignore
└── README.md
```

## What's deliberately not here

- No build tool, framework, bundler, or package.json.
- No PDFs in the repo — link to arXiv / external hosts instead.
- No Google Analytics or tracking. Add later if desired.
