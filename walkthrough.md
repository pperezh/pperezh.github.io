# Project Walkthrough & Deployment Guide

## Previous Work: Refining Publications & Projects Display

I have implemented custom displays for both Publications and Projects sections.

### Key Changes
- **Content Sync**: Synced all publication content from `source_info/content/publications` to `content/publications`.
- **Publications Layouts**:
    - `layouts/publications/list.html`: Standard width (`max-w-7xl`), left-aligned list with PDF/DOI links.
    - `layouts/publications/single.html`: Stacked layout (Image -> Abstract -> Content) using full width of the standard container.
- **Projects Configuration**:
    - Disabled year grouping (`groupByYear: false`).
    - Enabled card view (`view: "card"`).
    - **Reversion**: Removed custom `layouts/projects/list.html` and overlay partials because they caused display issues (blank screen). The section now relies on the standard theme layout, which respects the `view: "card"` and `groupByYear: false` settings.

### Verification
- **Projects**: Restored to standard theme card layout.
- **Publications**: Verified stacked details view.

---

## How to Link This Project to GitHub

### 1. Rename/Create Repository
Ensure your repository on GitHub is named **`pperezh.github.io`** (case-sensitive).

### 2. Update Local Git Remote
Point your local project to this new repository:

```bash
git remote set-url origin https://github.com/pperezh/pperezh.github.io.git
```

### 3. Push Your Integrity Check
Push your code (including the new GitHub Action I just added):

```bash
git add .
git commit -m "feat: add github action for pages deployment"
git push origin main
```

---

## Setting up GitHub Pages (Crucial Step)

After pushing the code, you must configure the repository on GitHub:

1.  Go to your repository **Settings** tab.
2.  Click on **Pages** in the left sidebar.
3.  Under **"Build and deployment"**:
    *   **Source**: Select **GitHub Actions** (Beta) from the dropdown menu.
4.  That's it! GitHub will detect the `hugo.yaml` file I created and automatically start building your website.

You can check the progress in the **Actions** tab of your repository.
1. Click on the **Actions** tab.
2. You should see a workflow run named **"chore: remove redundant CNAME and trigger deploy"** (or similar) queued or running.
3. Click on it to watch the steps.
4. Once it completes effectively, the `Deploy` step will show a green checkmark, and your site will be live at `https://pperezh.github.io`.

**UPDATE:** The workflow has been fixed and successfully deployed! 🟢

### Solution Summary
1.  **Hugo Version**: Bumped to `0.141.0` (Extended) to support the latest Blowfish theme features (specifically the `try` function).
2.  **Sass Installation**: Switched to `npm install -g sass` for reliable CSS compilation.
3.  **Custom Domain**: Temporarily removed `CNAME` to unblock the build.

### Next Step: Restore Custom Domain
Now that the site is building correctly, you can re-connect your custom domain:

1.  **Verify Removal**: Ensure `www.pperezh.com` is **completely removed** from your *old* repository's settings on GitHub.
2.  **Add `static/CNAME`**: Create a file named `CNAME` inside the `static` folder (not the root) with the content:
    ```
    www.pperezh.com
    ```
3.  **Update Config**: Change the verified URL in `hugo.toml`:
    ```toml
    baseURL = "https://www.pperezh.com/"
    ```
4.  **Push Changes**:
    ```bash
    git add .
    git commit -m "chore: restore custom domain"
    git push origin main
    ```
5.  **GitHub Settings**: Go to Settings > Pages > Custom domain and verify it is set to `www.pperezh.com`.

---

## Managing Multi-Language Content

Your site now supports **English (default)** and **Spanish**.

### How to Edit Translations
1.  **Bio & CV**: Edit `content/_index.es.md` or `content/cv/_index.es.md`.
2.  **Projects & Publications**:
    *   I have cloned your existing content to `.es.md` files (e.g., `content/projects/MyProject/index.es.md`).
    *   Open these files and translate the `title`, `description`, and body text.
    *   **Tip**: If you delete an `.es.md` file, that specific page will disappear from the Spanish version of the site.

### Adding New Content
When you add a new project or publication:
1.  Create the English file normally: `index.md`.
2.  Create the Spanish copy in the same folder: `index.es.md`.

---

## AI Tools Tab

The **AI Tools** section (`/ai-tools/`) is a card-based list of posts reviewing or comparing AI tools relevant to research workflows. Each post is a folder under `content/ai-tools/`.

### How to Add a New AI Tools Post

1.  **Create a folder** under `content/ai-tools/` named after your post, e.g.:
    ```
    content/ai-tools/my-tool-review/
    ```

2.  **Create the English file** `content/ai-tools/my-tool-review/index.md` with this frontmatter:
    ```markdown
    ---
    title: "Your Post Title"
    date: YYYY-MM-DD
    description: "One-sentence description shown on the card."
    tags: ["AI", "tools"]
    ---

    Intro paragraph here.

    <!-- Paste your raw HTML below — it renders because hugo.toml has unsafe = true -->
    <style>
      /* your styles */
    </style>
    <div>
      <!-- your HTML table or widget -->
    </div>
    ```

3.  **Create the Spanish file** `content/ai-tools/my-tool-review/index.es.md` with the same structure, translated.

4.  **Embed raw HTML**: Since `hugo.toml` sets `markup.goldmark.renderer.unsafe = true`, you can paste any `<style>`, `<table>`, or `<div>` block directly inside the markdown file and it will render as-is. No shortcode needed.
    > **Critical:** Do NOT leave blank lines inside `<table>`, `<tbody>`, or `<div>` blocks. A blank line ends the HTML block and goldmark reverts to markdown — indented rows then become code blocks. Keep all rows on consecutive lines with no gaps.

5.  **Push to deploy**:
    ```bash
    git add content/ai-tools/
    git commit -m "feat: add AI tools post — your title"
    git push origin main
    ```
    GitHub Actions will rebuild the site automatically.

### Adding Links in Markdown (including email)

Standard markdown link syntax works anywhere in the text body:

```markdown
[link text](URL)
```

Examples:

| What you want | Syntax | Renders as |
| --- | --- | --- |
| Email hyperlink | `[patricio@pperezh.com](mailto:patricio@pperezh.com)` | clickable email |
| External URL | `[Scite.ai](https://scite.ai)` | clickable link |
| Internal page | `[Publications](/publications/)` | link to site section |

> **Avoid** the `<email@domain.com>` autolink shorthand — Hugo/goldmark can mangle it inside prose text. Always use the explicit `[text](mailto:email)` form instead.

### Structure Reference
```
content/ai-tools/
├── _index.md          ← section index (EN) — do not delete
├── _index.es.md       ← section index (ES) — do not delete
└── mcp-tools-ranked/
    ├── index.md       ← first post (EN) — MCP tools ranking table
    └── index.es.md    ← first post (ES)
```

