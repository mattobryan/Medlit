# 🚀 Deploy MedLit Search — Right Now

**Time needed: under 10 minutes. No coding required.**

---

## Option A — GitHub Desktop (easiest, no terminal)

### 1. Install GitHub Desktop
Download from https://desktop.github.com — install and sign in with your GitHub account.
If you don't have a GitHub account, create a free one at https://github.com/signup

### 2. Create a new repository
1. Open GitHub Desktop
2. Click **File** → **New Repository**
3. Fill in:
   - **Name:** `medlit-search`
   - **Description:** Medical literature search tool
   - **Local Path:** anywhere on your computer
   - ✅ Tick **Initialize this repository with a README**
4. Click **Create Repository**

### 3. Add the project files
1. Click **Show in Explorer** (Windows) or **Reveal in Finder** (Mac)
2. Copy ALL files from this project folder into that folder:
   - `index.html`
   - `README.md`
   - `404.html`
   - `.nojekyll`
3. Go back to GitHub Desktop — you'll see all the files listed as changes
4. At the bottom left, type a commit message: `Deploy MedLit Search`
5. Click **Commit to main**
6. Click **Publish repository** (top right)
7. Make sure **Keep this code private** is UNTICKED (must be public for free Pages)
8. Click **Publish Repository**

### 4. Enable GitHub Pages
1. Go to https://github.com/YOUR-USERNAME/medlit-search
2. Click **Settings** tab
3. Left sidebar → scroll to **Pages**
4. Under Source: select **Deploy from a branch**
5. Branch: **main** | Folder: **/ (root)**
6. Click **Save**

### 5. Live in 2 minutes ✅
Your URL will be:
```
https://YOUR-USERNAME.github.io/medlit-search/
```
GitHub will show a green banner in Settings → Pages when it's ready.

---

## Option B — Upload via GitHub.com (no software needed)

### 1. Create repository
1. Go to https://github.com/new
2. Repository name: `medlit-search`
3. Set to **Public**
4. Tick **Add a README file**
5. Click **Create repository**

### 2. Upload files one by one
1. On your repository page, click **Add file** → **Upload files**
2. Drag ALL project files into the upload box:
   - `index.html`
   - `README.md`
   - `404.html`
   - `.nojekyll`
3. Commit message: `Deploy MedLit Search`
4. Click **Commit changes**

### 3. Enable GitHub Pages
1. Click the **Settings** tab
2. Left sidebar → **Pages**
3. Source: **Deploy from a branch** → **main** → **/ (root)**
4. Click **Save**

### Done ✅
Wait 1–2 minutes, then visit:
```
https://YOUR-USERNAME.github.io/medlit-search/
```

---

## Option C — Git command line (fastest if you have Git installed)

```bash
# From inside the medlit-search project folder:
git init
git add .
git commit -m "Deploy MedLit Search"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/medlit-search.git
git push -u origin main
```
Then enable GitHub Pages in Settings → Pages as above.

---

## Verifying it works

Once deployed, open the URL and:
1. Type a topic in the search box (e.g. "postnatal depression")
2. Press Search
3. Results should stream in from all 6 databases within ~5 seconds
4. Click any "Find Free Version" button — Unpaywall will check for open-access copies
5. Scroll down to see the paywall database guides and workaround cards

> **If you see "Failed to fetch" errors:** You're testing inside Claude.ai's artifact viewer, which blocks outbound requests. This is a sandbox restriction — the live GitHub Pages URL works fine.

---

## Sharing the tool

Once live, your URL looks like:
```
https://YOUR-USERNAME.github.io/medlit-search/
```

You can share this with:
- Colleagues and students
- On WhatsApp, email, or LinkedIn
- Bookmark it on your phone for quick access

---

## Enabling AI Synthesis

The AI evidence summary requires an Anthropic API key:
1. Get a free key at https://console.anthropic.com (free tier available)
2. On the live site, click **⚙ Add API Key** in the header
3. Paste your key — it stays in your browser session only, never stored
4. Run a search — the AI panel appears automatically

---

## File reference

| File | Purpose |
|------|---------|
| `index.html` | The entire app — all code in one file |
| `README.md` | Documentation shown on GitHub |
| `404.html` | Handles direct URL access (prevents blank pages) |
| `.nojekyll` | Tells GitHub Pages not to run Jekyll (prevents build errors) |
| `CNAME.example` | Only needed if you have a custom domain — otherwise ignore |

---

## Updating the tool later

To change the default keywords, open `index.html` in any text editor (Notepad, TextEdit, VS Code) and find:
```javascript
const [kw, setKw] = useState("postnatal depression maternal mental health");
```
Change the text, save, and re-upload to GitHub. Changes go live in ~1 minute.
