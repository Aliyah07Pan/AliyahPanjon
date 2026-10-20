# Aliyah Panjon — UX/UI Portfolio

Personal portfolio site. Static HTML, no build step.

**Live site:** https://aliyah07pan.github.io/portfolio/ *(update once Pages is enabled)*

## Pages

| File | Page |
|---|---|
| `index.html` | Redirect to the homepage |
| `Portfolio.dc.html` | Home — hero, selected work |
| `AboutMe.dc.html` | About, skills, tools |
| `CaseStudy-Thearis.dc.html` | Thearis — AI financial dashboard |
| `CaseStudy-Chimera.dc.html` | Chimera — security camera app redesign |
| `CaseStudy-Archlog.dc.html` | ArchLog — design-decision tracker |

## Structure

```
index.html          Entry point, redirects to Portfolio.dc.html
*.dc.html           Pages (template + logic class in one file)
support.js          Rendering runtime — loads React, compiles the templates
image-slot.js       Image placeholder component
assets/             Images used by the pages
```

Each `.dc.html` file holds the page markup inside `<x-dc>` and its behavior in a
`<script type="text/x-dc">` block. `support.js` compiles both at load time and
mounts the result into `#dc-root`.

## Running locally

Open with a local server — opening the files directly with `file://` will block
the runtime's fetches.

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying with GitHub Pages

Settings → Pages → Source: *Deploy from a branch* → `main` / `root`.
`.nojekyll` is included so Jekyll doesn't reprocess the files.

## Notes

- `uploads/` and `screenshots/` are working folders and are gitignored.
- Only the images referenced by the pages live in `assets/`.
