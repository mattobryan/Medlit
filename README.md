# MedLit Search

**Intelligent clinical literature search across 6 free databases, with AI synthesis, open-access detection, and institutional proxy support.**

Search PubMed, Europe PMC, Semantic Scholar, OpenAlex, CrossRef, and DOAJ simultaneously. One-click access to 8 paywalled databases via your institution's EZproxy. AI-powered evidence synthesis, PICO framework search, smart query optimisation, and export in multiple citation formats — all in a single HTML file with no installation.

**Live:** [https://mattobryan.github.io/Medlit/](https://mattobryan.github.io/Medlit/)

---

## Features

| | Feature | Detail |
|---|---|---|
| 🔍 | **Parallel search** | All 6 free databases queried simultaneously; results stream in as they arrive |
| 🏛 | **Institutional proxy** | Configure your EZproxy URL once — all paper links route through it automatically |
| 🗝 | **Paywall one-click access** | CINAHL, Scopus, Cochrane, Web of Science, PsycINFO, AMED, ProQuest, MIDIRS — query pre-filled, opened via your proxy |
| ✦ | **Smart Search** | Claude reformulates your plain-English question into an optimised boolean query before hitting the APIs |
| 🤖 | **AI Evidence Synthesis** | Overview, key themes, study type breakdown, evidence quality rating, clinical implications, research gaps, and suggested follow-up searches |
| 🔓 | **Unpaywall** | Per-result and batch open-access checking via the Unpaywall API |
| 📐 | **PICO mode** | Structured Population / Intervention / Comparison / Outcome search builder |
| 🏷 | **Study type detection** | Auto-detects RCT, Systematic Review, Cohort, Qualitative, Cross-Sectional, and more from title and abstract |
| 📎 | **Citation counts** | Displayed where available (Semantic Scholar, OpenAlex, Europe PMC) |
| ⎘ | **Export** | Plain text, BibTeX, RIS, and CSV |
| 🔖 | **Bookmarks** | Save results within a session and filter to bookmarks only |
| 📅 | **Filters** | Year range, open-access only, auto-batch Unpaywall check |
| 📱 | **Responsive** | Full functionality on phone and tablet |

---

## Quick start

### 1 — Open the tool

Visit **[https://mattobryan.github.io/Medlit/](https://mattobryan.github.io/Medlit/)** in any browser.

No installation. No login. No cost.

### 2 — Configure settings (one-time, saved to your device)

Click **⚙** in the top-right corner.

| Field | What to enter | Where to get it |
|---|---|---|
| **API Key** | Your Anthropic API key (`sk-ant-…`) | [console.anthropic.com](https://console.anthropic.com) |
| **Institution** | Your organisation name | — |
| **EZproxy URL** | Your institution's proxy prefix | Your library IT team or library website |

Click **Save**. All three values are stored in your browser's `localStorage` — they persist across sessions on the same device and are never transmitted anywhere except the Anthropic API for the key.

**EZproxy URL format** — paste exactly what your library provides, typically:
```
https://ezproxy.yourinstitution.ac.uk/login?url=
```
Once set, every paper link (including all 8 paywall database buttons) routes through the proxy automatically. Authenticate once at your institution's login page per browser session — no further prompts.

### 3 — Search

Type a topic in the search bar and press **Search** or **Enter**.

Switch to **PICO mode** for structured clinical questions — fill in Population, Intervention, Comparison (optional), and Outcome fields and the tool builds the boolean query automatically.

Enable **Smart Search** (top-right toggle) to have Claude rewrite your query into optimised search terms with synonyms and boolean operators before the search fires.

---

## Institutional access to paywalled databases

After any search, a strip of paywall database buttons appears below the source tabs. Each button:

1. Has your current search query pre-filled
2. Opens through your EZproxy URL (if configured)
3. Takes you directly to results — authenticate once if prompted

**Covered databases:**

| Database | Coverage |
|---|---|
| CINAHL | Nursing, midwifery, allied health — 1937 to present |
| Scopus | Multidisciplinary — 90M+ records, 7,000+ publishers |
| Cochrane Library | Gold-standard systematic reviews and RCTs |
| Web of Science | High-impact journals, citation mapping — 1900 to present |
| PsycINFO | Psychology, psychiatry, psychosocial interventions |
| AMED | Allied and complementary medicine |
| ProQuest | Dissertations, theses, grey literature |
| MIDIRS | Specialist maternity and infant care literature |

---

## Free databases searched automatically

| Database | Coverage |
|---|---|
| **PubMed** | US National Library of Medicine — 35M+ biomedical records |
| **Europe PMC** | MEDLINE + Cochrane + preprints — full-text links where available |
| **Semantic Scholar** | AI-powered index — surfaces open-access PDFs automatically |
| **OpenAlex** | 250M+ scholarly works — fully open, abstract reconstruction |
| **CrossRef** | 150M+ DOI registry — broad cross-disciplinary metadata |
| **DOAJ** | Directory of Open Access Journals — peer-reviewed OA only |

---

## AI features

Both AI features require an Anthropic API key (set in ⚙ Settings).

### Smart Search
Rewrites your plain-English topic into a boolean search string with synonyms and MeSH-style terms before the query is sent to the databases. The enhanced query is shown below the search bar so you can see exactly what was used.

### AI Evidence Synthesis
After results load, Claude analyses up to 20 papers and returns:

- **Overview** — 3–4 sentence narrative synthesis of the evidence landscape
- **Study types** — breakdown of research designs found
- **Evidence level** — HIGH / MODERATE / LOW / MIXED rating
- **Key themes** — major topics across the result set
- **Clinical implications** — direct practice takeaways
- **Research gaps** — limitations and unanswered questions
- **Suggested searches** — clickable related queries

Model: `claude-opus-4-7`. A typical synthesis costs under $0.01.

---

## Finding free full text

**Unpaywall** is integrated at the result card level. Click **Find free version** on any result with a DOI to check for a legal open-access copy (preprint, repository version, or author manuscript).

Enable **Auto-check all results** in Filters to run Unpaywall checks automatically across all results after a search completes.

### Additional legal routes

| Method | Notes |
|---|---|
| **PubMed Central** | All NIH-funded research deposited here — free |
| **Open Access Button** | Finds preprints; can request copies from authors |
| **medRxiv / bioRxiv** | Preprint servers — free before journal publication |
| **Email the author** | Authors almost always share their own work |
| **Interlibrary Loan** | University or NHS library members — fulfilled in 24–48 hrs |

---

## Export formats

After a search, click **Export ▾** in the toolbar:

| Format | Use for |
|---|---|
| Plain text | Quick copy of titles + DOIs |
| BibTeX (`.bib`) | LaTeX, Overleaf |
| RIS (`.ris`) | Endnote, Mendeley, Zotero |
| CSV (`.csv`) | Excel, data analysis |

---

## Deploying your own instance

This is a single `index.html` file. No Node.js, no npm, no build step.

### GitHub Pages (recommended, free)

1. Fork or clone this repository
2. Go to **Settings → Pages → Source → GitHub Actions**
3. Push any change to `master` — the included workflow deploys automatically

The GitHub Actions workflow (`.github/workflows/deploy.yml`) deploys on every push to `master`.

### Run locally

Double-click `index.html` — it opens in your browser and works fully offline for the UI. API calls (database searches, Unpaywall, Anthropic) require an internet connection.

---

## Architecture

| | |
|---|---|
| **Framework** | React 18 (CDN) |
| **Transpilation** | Babel Standalone — JSX compiled in-browser |
| **Styling** | Pure CSS custom properties — no framework |
| **APIs** | PubMed eUtils, Europe PMC, Semantic Scholar, OpenAlex, CrossRef, DOAJ, Unpaywall, Anthropic |
| **AI model** | `claude-opus-4-7` |
| **Storage** | `localStorage` for settings; `sessionStorage` for search history |
| **Deployment** | GitHub Pages via GitHub Actions |
| **File size** | Single HTML file — loads in under 2 seconds on 4G |

No backend. No database. No authentication server. No data leaves the browser except API calls to the sources listed above.

---

## Known limitations

- **Semantic Scholar** rate-limits at ~100 requests per 5 minutes per IP. Under heavy concurrent use its results may be empty.
- **Babel in-browser compilation** adds ~2 seconds to the first page load. This is a one-time cost on each visit.
- **Paywalled databases** cannot be searched programmatically — the tool generates pre-filled URLs and routes them through EZproxy. Actual access depends on your institution's subscriptions.
- **AI synthesis** requires a valid Anthropic API key. Without one, the synthesis panel is not shown.

---

## License

MIT — free to use, modify, and redistribute.
