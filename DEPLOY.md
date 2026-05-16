# GitHub Deployment Guide
## How to publish this repository as a live portfolio site

---

## Step 1 — Create your GitHub account and repository

1. Go to **github.com** → sign up or log in
2. Click **+** (top right) → **New repository**
3. Name it **exactly**: `your-username.github.io`
   - Replace `your-username` with your actual GitHub username
   - Example: if your username is `jsmith-risk`, name the repo `jsmith-risk.github.io`
   - This exact naming activates GitHub Pages automatically
4. Set to **Public** · check **Add a README file** · click **Create repository**

---

## Step 2 — Upload your files

### Option A: GitHub web editor (no coding required)

1. On your repository page, click **Add file → Upload files**
2. Drag and drop the entire portfolio folder contents:
   - `index.html`
   - `README.md`
   - The `articles/` folder and all its `.html` files
3. Write a commit message: `Initial portfolio publish`
4. Click **Commit changes**

To upload the `articles/` folder: GitHub's web uploader supports folders — just drag the whole folder in.

### Option B: Git command line (faster for future updates)

```bash
# Clone your new repo
git clone https://github.com/your-username/your-username.github.io
cd your-username.github.io

# Copy your portfolio files in
cp /path/to/portfolio/* .
cp -r /path/to/portfolio/articles ./articles

# Stage, commit, push
git add .
git commit -m "Initial portfolio publish"
git push origin main
```

---

## Step 3 — Enable GitHub Pages

1. Go to your repository → **Settings** tab (top menu)
2. Left sidebar → **Pages**
3. Under **Source**: select **Deploy from a branch**
4. Branch: **main** | Folder: **/ (root)**
5. Click **Save**

Your site will be live at `https://your-username.github.io` within 1–3 minutes.

To check: Settings → Pages → you'll see a green banner with the live URL.

---

## Step 4 — Personalize before publishing

Search the files for these placeholder values and replace them:

| Placeholder | Replace with |
|------------|-------------|
| `YOUR-USERNAME` | Your GitHub username |
| `YOUR-PROFILE` | Your LinkedIn profile slug |
| `YOUR@EMAIL.COM` | Your professional email |
| `your-username.github.io` | Your actual live URL |

These appear in `index.html`, `README.md`, and the article template.

---

## Step 5 — Add article content

Each article page uses `articles/_template.html` as its base. To create a new article:

1. Copy `_template.html` → rename it (e.g. `fraud-typology.html`)
2. Replace the placeholder values:
   - `ARTICLE_TITLE` → your article title
   - `ARTICLE_SUBTITLE` → the subtitle/abstract
   - `LEVEL` → Foundational / Intermediate / Advanced / Strategic
   - `CONTENT` → your article body (use the HTML elements already in the template)
3. Update the table of contents links in the sidebar to match your `<h2 id="...">` headings
4. Upload/push the new file
5. Update `index.html` to link to it (change `href="#"` to `href="articles/your-file.html"` and update status badges)

---

## Step 6 — Add repository topics (discoverability)

On your repo homepage → click the ⚙ gear icon next to **About** → add topics:

```
fraud-prevention  financial-crime  aml  banking  risk-management
fincrime  fintech  compliance  deepfakes  identity-fraud
consumer-banking  fraud-detection
```

Topics surface your repo in GitHub's topic search — meaningful for FinTech and RegTech communities.

---

## Step 7 — Ongoing workflow for new articles

```bash
# Pull latest
git pull origin main

# Create new article (copy template)
cp articles/_template.html articles/new-article.html

# Edit the new file, then...
git add articles/new-article.html index.html
git commit -m "Publish: [article title]"
git push origin main
```

GitHub Pages auto-rebuilds within ~30 seconds of each push.

---

## Step 8 — Link everything together

Once live, add your GitHub Pages URL to:

- **LinkedIn** profile → Website field → `https://your-username.github.io`
- **Email signature** → link with label "Fraud Risk Knowledge Repository"
- **LinkedIn articles** → end each post with: *"Full analysis at [url]"*
- **Publication pitches** → include the URL as evidence of your publication track record

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| Site not loading after 5 min | Settings → Pages → confirm branch is `main` and folder is `/` |
| Article links 404ing | Check that file names in `href=` exactly match the actual filenames (case-sensitive) |
| Changes not appearing | Hard refresh with Ctrl+Shift+R — GitHub Pages has a short cache |
| `articles/` folder not uploading | Upload files individually if the folder drag fails in the web editor |

---

*Once you've published, pin the repository on your GitHub profile: Profile → Customize profile → Pin repositories.*
