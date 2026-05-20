# Academic Homepage — Hafiz Muhammad Sanaullah Badar

A professional, modular academic website built for GitHub Pages.
No frameworks, no build step — pure HTML, CSS, and JavaScript.

## Live Site

> After deploying, your site will be at:
> `https://YOUR-GITHUB-USERNAME.github.io/`

---

## Project Structure

```
├── index.html            ← Home page (profile + bio + highlights + news)
├── research.html         ← Research areas and projects
├── publications.html     ← Full publication list with filters
├── software.html         ← Code releases and technical skills
├── team.html             ← Collaborators and students
├── services.html         ← Teaching, peer review, outreach
├── awards.html           ← Grants, awards, education, positions
│
├── data/                 ← ★ EDIT THESE FILES to update content
│   ├── profile.js        ← Personal info, bio, social links, metrics
│   ├── publications.js   ← All publications + manuscripts under review
│   ├── research.js       ← Research areas and projects
│   └── awards.js         ← Grants, awards, education, positions, services
│
├── assets/
│   ├── css/style.css     ← All styles (edit for visual changes)
│   ├── js/components.js  ← Shared rendering logic (nav, footer, pub card)
│   └── images/
│       └── profile.jpg   ← ★ ADD YOUR PHOTO HERE
│
└── README.md             ← This file
```

---

## Quick Start — Deploying to GitHub Pages

### Step 1: Add Your Photo

Copy your profile photo to `assets/images/` and name it `profile.jpg`.

```bash
cp /path/to/your/photo.jpg assets/images/profile.jpg
```

### Step 2: Update Your Personal Info

Open `data/profile.js` and update:

```js
// Change name, title, email, social links:
const PROFILE = {
  name:  "Hafiz Muhammad Sanaullah Badar",
  email: "badar@henu.edu.cn",
  socialLinks: [
    { label: "Google Scholar", url: "https://scholar.google.com/citations?user=YOUR_ID", ... },
    { label: "GitHub",         url: "https://github.com/YOUR_USERNAME",                  ... },
    ...
  ],
};
```

### Step 3: Push to GitHub

```bash
git init
git add .
git commit -m "Initial academic homepage"
git remote add origin https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io
git push -u origin main
```

> **Tip:** If you name the repository `YOUR-USERNAME.github.io`, it becomes your root GitHub Pages site.

### Step 4: Enable GitHub Pages

1. Go to your repository → **Settings** → **Pages**
2. Under **Source**, select `main` branch, `/ (root)` folder
3. Click **Save**

Your site will be live at `https://YOUR-USERNAME.github.io` within a few minutes.

---

## How to Update Each Section

### Add a New Publication

Open `data/publications.js` and paste a new entry at the **top** of the `PUBLICATIONS` array:

```js
{
  id: "pub-2026-my-new-paper",   // unique, lowercase-hyphen
  year: 2026,
  title: "My Awesome Paper Title",
  authors: "<strong>H. M. S. Badar</strong>, Co-Author One, Co-Author Two",
  venue: "IEEE Transactions on Something",
  venueShort: "IEEE ToS",
  volume: "14", issue: "3", pages: "100–110",
  doi: "10.1109/TOS.2026.XXXXXXX",  // without "https://doi.org/"
  arxiv: "",   // arXiv ID, e.g. "2301.00001" — leave empty if none
  code: "",    // GitHub URL — leave empty if none
  pdf:  "",    // Direct PDF URL — leave empty if none
  highlight: true,           // true = shown on homepage
  role: "First Author",      // "First Author" | "Corresponding Author" | ""
  rank: "Q1",                // "Q1" | "Q2" | "Q3" | "Conference" | ""
  tags: ["Smart Grid", "AI"],
},
```

### Add News Items

Open `index.html` and find the `NEWS` array near the bottom:

```js
const NEWS = [
  { date: "Jun 2026", text: "Paper accepted at IEEE TSG." },
  // paste new entries here at the top
];
```

### Add a Research Area

Open `data/research.js` and paste into `RESEARCH_AREAS`:

```js
{
  id: "quantum-security",
  icon: "🔐",
  title: "Quantum-Safe Cryptography",
  description: "Research on post-quantum cryptographic protocols for ...",
  tags: ["Post-Quantum", "Lattice Cryptography"],
  featured: true,
},
```

### Add an Award or Grant

Open `data/awards.js` and paste into `AWARDS`:

```js
{ year: 2026, title: "Best Paper Award", org: "IEEE XYZ Conference", amount: "", type: "award", description: "" },
```

### Add a Collaborator

Open `team.html` and paste into the `COLLABORATORS` array:

```js
{
  name: "Prof. Full Name",
  role: "Professor of XYZ",
  org: "University Name, Country",
  url: "https://their-homepage.com",
  coauthored: 2,
},
```

### Add a Software Release

Open `software.html` and paste into the `SOFTWARE` array:

```js
{
  title: "My Tool Name",
  desc: "Short description of the tool.",
  paper: "pub-2026-my-new-paper",   // matching id from publications.js
  github: "https://github.com/USERNAME/repo",
  demo: "",
  tags: ["Python", "PyTorch"],
  year: 2026,
},
```

---

## Customisation

### Change Colours

Open `assets/css/style.css` and edit the CSS variables at the top:

```css
:root {
  --primary:     #1a56b0;   /* main blue  */
  --accent:      #2e86de;   /* link hover */
  --bg:          #f0f0f0;   /* page background */
  --card:        #ffffff;   /* card background  */
}
```

### Change Navigation Order

Open `assets/js/components.js` and edit `NAV_ITEMS`:

```js
const NAV_ITEMS = [
  { label: "Home",         href: "index.html"        },
  { label: "Research",     href: "research.html"     },
  // reorder, rename, or add pages here
];
```

---

## Local Preview (no install required)

Open `index.html` in any modern browser.
For best results, serve it locally to avoid CORS issues:

```bash
# Python 3
python -m http.server 8080
# then open http://localhost:8080
```

---

## File Editing Quick Reference

| What to change           | File to edit              |
|--------------------------|---------------------------|
| Name, photo, bio, email  | `data/profile.js`         |
| Publications             | `data/publications.js`    |
| Research areas           | `data/research.js`        |
| Awards, grants, education| `data/awards.js`          |
| News items               | `index.html` (NEWS array) |
| Software releases        | `software.html`           |
| Teaching courses         | `services.html`           |
| Collaborators / students | `team.html`               |
| Colours & fonts          | `assets/css/style.css`    |
| Navigation links         | `assets/js/components.js` |

---

*Built with plain HTML/CSS/JS — no build tools, no dependencies.*
