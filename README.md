# FinanceCat — CFA, FRM & Quant Finance Study Notes

A personal finance study site hosted on GitHub Pages. Covers CFA, FRM, and Quantitative Finance — with a cat album on the side.

---

## Folder structure

This is the complete structure of the repo. Everything lives exactly where it should — nothing moves.

```
financecat/                          ← root of your GitHub repo
│
├── index.html                       ← Homepage
├── study.html                       ← Subject & chapter list
├── chapter.html                     ← Chapter reader (renders .md files)
├── cats.html                        ← Cat photo album
├── README.md                        ← This file
│
├── cats/                            ← 📷 ALL cat photos go here
│   ├── index.json                   ← List of photo filenames (you update this)
│   ├── sleeping-on-textbook.jpg     ← Your cat photos (any JPG/PNG/WEBP)
│   ├── monday-morning.jpg
│   └── ...
│
└── content/                         ← 📚 ALL study content goes here
    │
    ├── cfa/                         ← 📁 CFA chapters
    │   ├── index.json               ← CFA chapter list (you update this)
    │   ├── overview.md              ← Written ✓
    │   ├── l1-ethics.md             ← Written ✓
    │   ├── l1-quant.md              ← Written ✓
    │   ├── l1-economics.md          ← Add your own
    │   ├── l1-fra.md                ← Add your own
    │   ├── l1-corporate.md          ← Add your own
    │   ├── l1-equity.md             ← Add your own
    │   ├── l1-fi.md                 ← Add your own
    │   ├── l1-derivatives.md        ← Add your own
    │   ├── l1-alternatives.md       ← Add your own
    │   └── l1-portfolio.md          ← Add your own
    │
    ├── frm/                         ← 📁 FRM chapters
    │   ├── index.json               ← FRM chapter list (you update this)
    │   ├── overview.md              ← Add your own
    │   ├── p1-quant.md              ← Add your own
    │   ├── p1-foundations.md        ← Add your own
    │   ├── p1-financial-markets.md  ← Add your own
    │   ├── p1-valuation.md          ← Add your own
    │   ├── p2-market.md             ← Add your own
    │   ├── p2-credit.md             ← Add your own
    │   ├── p2-operational.md        ← Add your own
    │   ├── p2-liquidity.md          ← Add your own
    │   └── p2-investment.md         ← Add your own
    │
    ├── quant/                       ← 📁 Quantitative Finance chapters
    │   ├── index.json               ← Quant chapter list (you update this)
    │   ├── overview.md              ← Written ✓
    │   ├── probability.md           ← Written ✓
    │   ├── linear-algebra.md        ← Add your own
    │   ├── calculus.md              ← Add your own
    │   ├── stochastic.md            ← Add your own
    │   ├── options-pricing.md       ← Add your own
    │   ├── risk-models.md           ← Add your own
    │   ├── time-series.md           ← Add your own
    │   └── ml-finance.md            ← Add your own
    │
    └── general/                     ← 📁 General Finance chapters
        ├── index.json               ← General chapter list (you update this)
        ├── overview.md              ← Add your own
        ├── time-value.md            ← Add your own
        ├── financial-statements.md  ← Add your own
        ├── portfolio-theory.md      ← Add your own
        └── market-efficiency.md     ← Add your own
```

---

## The two rules

**Rule 1 — The filename must match the id in index.json.**

If your file is `l1-equity.md`, the id in `index.json` must be `"l1-equity"`. That's it.

**Rule 2 — Always update index.json when adding a new chapter.**

The HTML reads `index.json` to know which chapters exist. If you upload a `.md` file but don't add it to `index.json`, it won't appear in the chapter list.

---

## How to add a new chapter (step by step)

### Step 1 — Write your content as a Markdown file

Create a new `.md` file in the correct subject folder. You can write in any text editor, or write in Word and paste the content into a `.md` file.

**Example:** `content/cfa/l1-equity.md`

```markdown
# Equity Investments

Intro paragraph here.

## Market structure

Content here. You can use:

**Bold text**, *italic text*, `inline code`

## Key formulas

| Formula | Description |
|---------|-------------|
| P/E     | Price / Earnings |

> Important callout — use blockquotes for key exam tips

- Bullet points work
- Like this

1. Numbered lists
2. Work too
```

### Step 2 — Add it to the chapter index

Open `content/cfa/index.json` and add one entry to the array:

```json
[
  ...existing chapters...,
  {
    "id": "l1-equity",
    "title": "Equity Investments",
    "level": "Level 1",
    "description": "Market structure, equity securities, and valuation fundamentals."
  }
]
```

- `id` — must exactly match the filename without `.md`
- `title` — shown in the chapter list
- `level` — used to group chapters (e.g. "Level 1", "Level 2", "Part 1", "Foundations")
- `description` — short summary shown under the title in the list

### Step 3 — Push to GitHub

```bash
git add content/cfa/l1-equity.md content/cfa/index.json
git commit -m "Add Equity Investments chapter"
git push
```

The chapter appears on the site immediately. No code changes needed, ever.

---

## How to add cat photos (step by step)

### Step 1 — Add your photo files

Copy your photos into the `cats/` folder. Any JPG, PNG, or WEBP file works.

**Naming tip:** Use descriptive names with hyphens — the filename becomes the caption automatically.
- `sleeping-on-textbook.jpg` → caption: "sleeping on textbook"
- `monday-morning-chaos.jpg` → caption: "monday morning chaos"

### Step 2 — Update cats/index.json

Open `cats/index.json` and add each filename:

```json
[
  "sleeping-on-textbook.jpg",
  "monday-morning-chaos.jpg",
  "exam-panic.png",
  "helping-with-derivatives.jpg"
]
```

### Step 3 — Push to GitHub

```bash
git add cats/ cats/index.json
git commit -m "Add cat photos"
git push
```

The homepage will now randomly pick one photo on every visit. The album page shows them all in a masonry grid with a lightbox viewer (click to open, arrow keys to navigate).

---

## Enabling GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** → **Pages**
3. Under **Source**, select **Deploy from a branch**
4. Set branch to `main` and folder to `/ (root)`
5. Click **Save**

Your site will be live at `https://your-username.github.io/financecat/` within a few minutes.

> **Important:** The site fetches `.json` and `.md` files dynamically, so it must be served over HTTP — either via GitHub Pages or a local server. Opening the HTML files directly from your file system (double-clicking) will NOT work due to browser security restrictions.

---

## Running locally before pushing

```bash
# Option 1 — Python (no install needed)
python3 -m http.server 8000
# then open http://localhost:8000

# Option 2 — Node
npx serve .
# then open the URL it shows
```

---

## Markdown quick reference

| You type | You get |
|----------|---------|
| `# Title` | Big heading (h1) |
| `## Section` | Section heading (h2) |
| `### Sub-section` | Sub-heading (h3) |
| `**bold**` | **bold** |
| `*italic*` | *italic* |
| `` `code` `` | inline code |
| `> text` | blockquote / callout box |
| `- item` | bullet point |
| `1. item` | numbered list |
| `---` | horizontal rule |
| `[text](url)` | hyperlink |
| `\| col \| col \|` | table row |

---

## Pages overview

| File | What it does |
|------|-------------|
| `index.html` | Homepage — shows a random cat photo from `cats/`, links to all 4 subjects |
| `study.html` | Subject switcher and chapter list — reads each `index.json` |
| `chapter.html` | Chapter reader — fetches and renders any `.md` file, shows sidebar nav |
| `cats.html` | Cat album — masonry grid from `cats/index.json`, lightbox on click |

---

## Tech stack

- Pure HTML, CSS, JavaScript — no frameworks, no build step, no install
- [Marked.js](https://marked.js.org/) for Markdown rendering (loaded from CDN)
- Google Fonts — Lora + DM Sans (study pages), Caveat (cat album)
- GitHub Pages for free hosting
- Zero backend — everything is static files
