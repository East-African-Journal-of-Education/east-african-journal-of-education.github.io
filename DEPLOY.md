# East African Journal — GitHub Pages Deployment Guide

**Journal:** East African Journal of Educational, Social Science and Humanities Research  
**ISSN:** 2708-8111  
**Site URL:** https://eajournalesshresearch.github.io  
**Contact:** francisogula@yahoo.com

---

## Prerequisites

- A **GitHub account** (free) — create one at https://github.com if you don't have one
- The site files are in: `/home/francis/.openclaw/workspace/journal_site/`

---

## Step 1: Create the Repository

1. Log into GitHub
2. Click the **+** icon (top right) → **New repository**
3. Repository name: **`eajournalesshresearch.github.io`** (must be exactly this)
4. Set to **Public**
5. Leave everything else unchecked
6. Click **Create repository**

---

## Step 2: Upload the Site Files

### Option A: Drag & Drop (easiest)

1. On the empty repo page, click **"uploading an existing file"**
2. In your file manager, open `/home/francis/.openclaw/workspace/journal_site/`
3. Select **all files and folders** inside:
   - `index.html`
   - `about.html`
   - `contact.html`
   - `editorial-board.html`
   - `submissions.html`
   - `css/` (entire folder)
   - `issues/` (entire folder)
   - `pdfs/` (entire folder)
4. Drag them into the GitHub upload area
5. Scroll down, add a commit message like `"Initial site upload"`
6. Click **Commit changes**

### Option B: Command Line (if you have git set up)

```bash
cd /home/francis/.openclaw/workspace/journal_site
git init
git checkout -b main
git add .
git commit -m "Initial site"
git remote add origin https://github.com/YOUR_USERNAME/eajournalesshresearch.github.io.git
git push -u origin main
```

---

## Step 3: Wait for Deployment

GitHub Pages usually takes **1–2 minutes** to deploy. Your site will be live at:

**https://eajournalesshresearch.github.io**

To check status: Go to your repo → **Settings** → **Pages** — it should show "Your site is published at..."

---

## How to Add New Issues

When you publish a new volume:

1. **Add the article PDFs:**
   - Create a new folder: `pdfs/vol-6-2026/`
   - Name files like `01_Author_Topic.pdf`, `02_Author_Topic.pdf`, etc.

2. **Create a new issue page:**
   - Copy an existing issue page like `issues/vol-5-2025.html`
   - Update the volume number, year, and article list with titles and authors

3. **Update the home page and archives:**
   - Add the new issue to `index.html` (under "All Issues")
   - Add it to `issues/index.html`

4. **Upload to GitHub:**
   - Push the new/updated files to the repository

---

## Getting Found on Google

1. Go to https://search.google.com/search-console
2. Add your site URL
3. Verify ownership — choose **"HTML tag"** method:
   - Copy the meta tag they give you
   - Add it to the `<head>` section of `index.html`
   - Re-upload `index.html` to GitHub
   - Click **Verify**
4. Submit a sitemap (optional — I can generate one)

---

## Site File Structure

```
journal_site/
├── index.html              # Home page
├── about.html              # Aims & scope
├── contact.html            # Contact info
├── editorial-board.html    # Editorial board list
├── submissions.html        # Author guidelines
├── css/
│   └── style.css           # Styling
├── issues/
│   ├── index.html          # All issues listing
│   ├── vol-1-2020.html     # Vol 1 (June 2020)
│   ├── vol-2-2021.html     # Vol 2 (Sep 2021)
│   ├── vol-3-2023.html     # Vol 3 (Aug 2023)
│   ├── vol-4-2024.html     # Vol 4 (Aug 2024)
│   └── vol-5-2025.html     # Vol 5 (Aug 2025)
└── pdfs/
    ├── vol-1-2020/         # 5 articles
    ├── vol-2-2021/         # 6 articles
    ├── vol-3-2023/         # 6 articles
    ├── vol-4-2024/         # 7 articles
    └── vol-5-2025/         # 3 articles
```

---

## Notes

- All hosting is **$0/month** on GitHub Pages
- The site is **static HTML** — no database, no server, no security updates
- PDFs are served directly — readers click and download
- To update any page, just edit the HTML file and push to GitHub
