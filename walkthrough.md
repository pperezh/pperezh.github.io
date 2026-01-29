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

You have already created a blank repository on GitHub. Follow these steps to push your local code to that repository.

### 1. Initialize Git in your project folder
Open your terminal, ensure you are in the project directory (`/Users/pperezh/hugo-website`), and run:

```bash
git init
```

### 2. Add all files to the staging area
This prepares every file in your project to be saved (committed).

```bash
git add .
```

### 3. Commit your changes
This saves the current state of your project.

```bash
git commit -m "Initial commit of Hugo website"
```

### 4. Rename the branch to 'main' (if not already)
Standard practice is to use `main` as the default branch name.

```bash
git branch -M main
```

### 5. Link your local project to the GitHub repository
Replace `<YOUR_REPO_URL>` with the actual URL of your blank GitHub repository (e.g., `https://github.com/pperezh/my-website.git`).

```bash
git remote add origin <YOUR_REPO_URL>
```

### 6. Push your code to GitHub
This uploads your code to the remote repository.

```bash
git push -u origin main
```

---
**Note**: If you make future changes, you only need to run:
1. `git add .`
2. `git commit -m "Description of changes"`
3. `git push`
