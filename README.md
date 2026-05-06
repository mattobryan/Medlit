# MedLit Search

**Search 6 free medical databases simultaneously, find open-access papers via Unpaywall, and get AI-powered evidence synthesis.**

Live search across PubMed, Europe PMC, Semantic Scholar, OpenAlex, CrossRef, and DOAJ — plus guided one-click access to 8 paywalled databases (CINAHL, Scopus, Web of Science, ProQuest, MIDIRS, AMED, PsycINFO, Cochrane) and legal workaround resources.

---

## Deploy to GitHub Pages in 5 minutes

### Step 1 — Create a new GitHub repository

1. Go to [github.com](https://github.com) and sign in (or create a free account)
2. Click the **+** button (top right) → **New repository**
3. Name it something like `medlit-search`
4. Set it to **Public** (required for free GitHub Pages)
5. Leave all other settings as default
6. Click **Create repository**

### Step 2 — Upload the file

1. On your new repository page, click **Add file** → **Upload files**
2. Drag and drop `index.html` into the upload area
3. Scroll down, add a commit message like `"Initial deployment"`, and click **Commit changes**

### Step 3 — Enable GitHub Pages

1. In your repository, click the **Settings** tab (top navigation)
2. In the left sidebar, scroll down and click **Pages**
3. Under **Source**, click the dropdown and select **Deploy from a branch**
4. Under **Branch**, select `main` and leave the folder as `/ (root)`
5. Click **Save**

### Step 4 — Your app is live

After 1–2 minutes, GitHub Pages will show you a green banner with your live URL:

```
Your site is live at: https://YOUR-USERNAME.github.io/medlit-search/
```

Visit that URL — the tool is fully functional. Share it with anyone.

---

## Features

| Feature | Details |
|---------|---------|
| **6 Free Databases** | PubMed, Europe PMC, Semantic Scholar, OpenAlex, CrossRef, DOAJ — all searched simultaneously |
| **Result Format** | Title → Abstract summary → Direct link, for every paper |
| **Unpaywall Integration** | Click "Find Free Version" on any result to check for legal open-access copies |
| **AI Evidence Synthesis** | Paste your Anthropic API key to get an evidence overview, key themes, and research gap analysis |
| **Guided Paywall Access** | Step-by-step instructions for CINAHL, Scopus, WoS, ProQuest, MIDIRS, AMED, PsycINFO, Cochrane |
| **Legal Workarounds** | 6 ways to access paywalled papers for free (Unpaywall, OA Button, PMC, medRxiv, ILL, author email) |
| **Copy All References** | One click copies all visible results as formatted references |

---

## Using AI Synthesis

The AI synthesis feature requires an Anthropic API key:

1. Click the **⚙ Add API Key** button in the top-right of the header
2. Paste your key (starts with `sk-ant-...`) — get one at [console.anthropic.com](https://console.anthropic.com)
3. Click **Save** — the key is kept only for your current browser session, never stored or transmitted anywhere except directly to the Anthropic API
4. Run a search — the AI panel will appear automatically once results load

> **Note:** AI synthesis uses the `claude-opus-4-5` model. A typical synthesis costs less than $0.01.

---

## Why results don't appear in the Claude artifact viewer

If you're testing inside Claude.ai, the APIs return "Failed to fetch" errors. This is because the Claude artifact sandbox blocks outbound network requests as a security measure. The same code works perfectly on GitHub Pages because browsers can reach these APIs directly — they all support CORS.

---

## Databases covered

### Free (searched automatically)
- **PubMed** — US National Library of Medicine, 35M+ records
- **Europe PMC** — covers MEDLINE, Cochrane, and preprints
- **Semantic Scholar** — AI-powered index with open-access PDF links
- **OpenAlex** — 250M+ scholarly works, fully open
- **CrossRef** — metadata registry for 150M+ DOIs
- **DOAJ** — Directory of Open Access Journals (OA papers only)

### Paywalled (guided one-click access)
- CINAHL — nursing and allied health
- Scopus — multidisciplinary, 90M+ records
- Web of Science — citation mapping, high-impact journals
- ProQuest — dissertations, theses, grey literature
- MIDIRS — maternity and infant care
- AMED — allied and complementary medicine
- PsycINFO — psychology and mental health
- Cochrane Library — systematic reviews and RCTs

---

## Customising default keywords

Open `index.html` in any text editor and find this line near the top of the script:

```javascript
const [kw, setKw] = useState("postnatal depression maternal mental health");
```

Change the default search string to whatever topic is relevant for your work.

---

## No build step required

This is a single-file app. No Node.js, no npm, no build pipeline. React and Babel load from CDN at runtime. The trade-off is a ~2 second initial load while Babel compiles the JSX — acceptable for a research tool used occasionally.

---

## License

MIT — use, modify, and share freely.
