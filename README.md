# Abdul Manan Khan — Portfolio

A free, local-first, framework-free portfolio built with plain HTML, CSS, and JavaScript.

## Project structure

```
portfolio/
├── index.html                  ← homepage (all sections)
├── css/
│   └── style.css               ← entire design system lives here
├── js/
│   └── script.js                ← nav, filters, scroll effects
├── assets/
│   ├── images/projects/        ← put project screenshots here
│   └── icons/                  ← (icons currently load from a CDN, see below)
└── projects/
    ├── urbanedge.html
    ├── hotel-performance.html
    ├── credit-card-approval.html
    └── customer-segmentation.html
```

## Running it locally on Windows

You don't strictly need a server for a static site like this, but a local server avoids
a few quirks (some browsers restrict things when opening files directly via `file://`).

**Easiest method — VS Code Live Server (free):**
1. Open the `portfolio` folder in VS Code (`File → Open Folder`).
2. Install the **Live Server** extension (search it in the Extensions panel).
3. Right-click `index.html` → **Open with Live Server**.
4. Your site opens at something like `http://127.0.0.1:5500`.

**Alternative — Python's built-in server (if you have Python installed):**
```
cd path\to\portfolio
python -m http.server 8000
```
Then open `http://localhost:8000` in Chrome.

## How to edit content

- **Text content**: open `index.html` in VS Code and edit directly — it's plain, readable HTML with comments marking each section (`<!-- ============ HERO ============ -->` etc.).
- **Colors**: all colors are defined once at the top of `css/style.css` under `:root { ... }`. Change a value there (e.g. `--accent: #3FB8A3;`) and it updates everywhere.
- **Fonts / spacing / radius**: same place, `:root` in `style.css`.

## How to add a new project

1. **Screenshot(s)**: save into `assets/images/projects/your-project-name/`.
2. **Case study page**: copy any existing file in `projects/` (e.g. `hotel-performance.html`), rename it, and edit the text between the `<!-- ... -->` comments. Replace the placeholder `<div class="project-thumb">` text with an actual `<img>` tag pointing to your screenshot once you have one:
   ```html
   <img src="../assets/images/projects/your-project-name/thumb.png" alt="Description of the screenshot">
   ```
3. **Card on the homepage**: in `index.html`, copy one of the `<a class="project-card">` blocks inside `#projects`, update the title, description, tags, category (`data-category="ml" | "bi" | "automation" | "systems"`), and the link to your new case study page.
4. **Skills**: if the new project uses a skill not already listed, add a `<span class="tag">YourSkill</span>` under the right category in the `#skills` section.

## How to add a screenshot to an existing project

Replace the placeholder div:
```html
<div class="project-thumb">Screenshot: ...</div>
```
with:
```html
<img src="../assets/images/projects/project-name/thumb.png" alt="Description" style="width:100%; height:100%; object-fit:cover;">
```
(keep the parent `.project-thumb` or `.case-thumb-full` wrapper for correct sizing).

## How to update experience / education

Both live directly in `index.html`, in the `#experience` and `#education` sections — plain text, no build step needed. Just edit and save.

## Deploying later (free options, when you're ready)

You don't need this now, but when you want the site live on the internet instead of just localhost, all of these are free and work with a plain HTML/CSS/JS site — no code changes needed:
- **GitHub Pages** — push this folder to a GitHub repo, enable Pages in settings.
- **Netlify** or **Vercel** — drag-and-drop the `portfolio` folder into their free tier.

## Notes

- Icons load from a free CDN (Tabler Icons via jsdelivr) — you need an internet connection for icons to display, but no account, key, or payment is required.
- Fonts (Inter, JetBrains Mono) load from Google Fonts — same deal, free, no signup.
- No backend, no database, no paid services anywhere in this project.
