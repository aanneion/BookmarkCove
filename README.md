<div align="center">

# 🔖 BookmarkCove

**A free, private bookmark manager that runs 100% in your browser.**

Import from any browser → clean up, tag, dedupe, reorganize → export a file that imports anywhere.

[**Live Demo →**](https://bookmarkcove.vercel.app/) · [Report a Bug](https://github.com/aanneion/bookmarkcove/issues) · [Request a Feature](https://github.com/aanneion/bookmarkcove/issues)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![License: MIT](https://img.shields.io/badge/License-MIT-2f6feb?style=flat-square)
![No Trackers](https://img.shields.io/badge/tracking-none-2f6feb?style=flat-square)
![100% Local](https://img.shields.io/badge/data-local-2f6feb?style=flat-square)
![PWA Ready](https://img.shields.io/badge/PWA-ready-2f6feb?style=flat-square)

</div>

---

## 📖 About

**BookmarkCove** is a single-file, offline-first bookmark manager built for people who are tired of bloated bookmark extensions that demand an account, upload their data to a server, and track everything they click.

Every major browser can export bookmarks as a Netscape-format `bookmarks.html` file (and you can also bring in JSON, JSONL, or CSV from anywhere). BookmarkCove reads your file, presents it as a clean, searchable folder tree, and lets you curate it — bulk-select to clean up, drag to reorder, tag to organize, find duplicates in one click — before exporting a fresh file you can import back into Chrome, Firefox, Edge, Safari, Opera, or Brave.

Everything happens **in your browser**. Nothing is uploaded. There is no backend. There is no account.

---

## ✨ Features

### Import & Export
- 📥 **Multi-format import** — Netscape `bookmarks.html`, **JSON**, **JSONL / NDJSON**, **CSV** (auto-detects format)
- 📤 **Standards-compliant export** — Netscape bookmark file that imports into every major browser, folders and tags intact
- 🖱️ **Drag-and-drop or file picker** — Drop a file anywhere on the page

### Cleanup & Organization
- 🔍 **Instant search** — Filter by name, URL, or tag as you type (`/` or `⌘/Ctrl+K` to focus)
- ☑️ **Bulk-select** — Tick multiple bookmarks or an entire folder to move or delete at once
- ❌ **Delete / restore** — Cross out links or folders; the bottom bar restores everything
- ↗️ **Move bookmarks** — Reassign one or many links to a different folder from a dropdown
- 🎯 **Drag-and-drop reordering** — Drag a link onto another link to reorder, onto a folder to nest it
- 🏷️ **Tags / labels** — Add comma-separated tags per bookmark; chips show up inline and are included in search + export
- 🧬 **Duplicate detection** — One click finds URLs that appear more than once and removes the extras (restorable)

### Experience
- 🖼️ **Smart favicons** — Uses icons embedded in the export first, then DuckDuckGo — toggleable in Settings
- 🌗 **Light / dark / auto theme** — Follows your system or pick one manually
- 💾 **Auto-save** — Edits persist in `localStorage`; reload and everything is still there
- 📱 **Responsive** — Works on desktop, tablet, and mobile
- ⌨️ **Keyboard-friendly** — Skip-link, focus styles, `/` shortcut, `Esc` to close menus
- 📲 **Installable PWA** — Add to home screen; offline caching via service worker (optional `sw.js`)

### Privacy
- 🔒 **100% local** — No backend, no analytics, no tracking, no account, no cloud

---

## 🔐 Privacy

BookmarkCove was built privacy-first.

- **No server.** The app is a single static HTML file hosted on Vercel's CDN.
- **No tracking.** No Google Analytics, no cookies, no fingerprinting.
- **No account.** There is nothing to sign up for.
- **Data stays in your browser.** Your bookmarks are stored in `localStorage` under the key `bc-tree-v1`.
- **Favicons are optional.** If you enable "Site icons" in Settings, only the *domain name* of each bookmark is sent to DuckDuckGo's icon service. Turn it off and every link shows a generated letter badge instead, with zero outbound requests.

---

## 🚀 Getting Started

### Use the hosted version

Open [**bookmarkcove.vercel.app**](https://bookmarkcove.vercel.app/) and drop your bookmarks file onto the page.

### Run it locally

Single HTML file, no build step:

```bash
git clone https://github.com/aanneion/bookmarkcove.git
cd bookmarkcove
# Then open index.html in your browser, or:
npx serve .
```

### Deploy your own copy

**Option A — Vercel (recommended)**

1. Fork this repo
2. Go to [vercel.com/new](https://vercel.com/new) → import the forked repo
3. Click **Deploy**

**Option B — Vercel Drop (no Git)**

1. Download the repo as a ZIP and extract it
2. Go to [vercel.com/drop](https://vercel.com/drop) and drag the folder onto the page

**Option C — Any static host**

The core app is `index.html`. Drop it into GitHub Pages, Netlify, Cloudflare Pages, or any static file server.

---

## 📂 Project Structure

```
bookmarkcove/
├── index.html          # The entire application (HTML + CSS + JS)
├── sw.js               # Optional: service worker for offline caching
├── README.md           # This file
└── (optional SEO/PWA)
    ├── robots.txt
    ├── sitemap.xml
    ├── manifest.json
    ├── og-cover.png
    ├── apple-touch-icon.png
    ├── icon-192.png
    └── icon-512.png
```

The core app is deliberately a **single file** — no bundler, no dependencies, no build step. The service worker is the only optional companion file (skip it and the app still works, just without offline caching).

---

## 📥 Import Formats

| Format | Extension | Notes |
|---|---|---|
| **Netscape bookmarks** | `.html`, `.htm` | Native format for every major browser |
| **JSON** | `.json` | Array of `{ name, url, tags?, folder? }` |
| **JSONL / NDJSON** | `.jsonl`, `.ndjson` | One JSON object per line |
| **CSV** | `.csv` | Columns: `name`, `url`, `tags`, `folder` (case-insensitive) |

The importer auto-detects the format from the file extension, and falls back to sniffing the content if the extension is missing.

### CSV example

```csv
name,url,folder,tags
GitHub,https://github.com,Dev,code;git
MDN,https://developer.mozilla.org,Dev,reference;docs
```

---

## 🔄 How to Export Bookmarks From Your Browser

<details>
<summary><b>Google Chrome</b></summary>

1. Open `chrome://bookmarks`
2. Click the **⋮** menu (top right)
3. Select **Export bookmarks**
4. Save the file
</details>

<details>
<summary><b>Mozilla Firefox</b></summary>

1. Open `about:bookmarks` (or press `Ctrl/Cmd + Shift + O`)
2. Click **Import and Backup**
3. Select **Export bookmarks to HTML…**
4. Save the file
</details>

<details>
<summary><b>Microsoft Edge</b></summary>

1. Open `edge://favorites`
2. Click the **…** menu
3. Select **Export favorites**
4. Save the file
</details>

<details>
<summary><b>Safari</b></summary>

1. Go to **File → Export → Bookmarks…**
2. Save the file
</details>

<details>
<summary><b>Opera / Brave / Vivaldi</b></summary>

Same as Chrome — these browsers share the Chromium bookmark manager. Open the bookmark manager, find the export option, save the file.
</details>

Once exported, drop the file into BookmarkCove. After cleaning up, click **Export** to download a fresh `bookmarks.html`, then import it back into your browser.

---

## 🧠 How It Works

BookmarkCove is a small, dependency-free JavaScript application:

1. **Parse** — Reads the file and parses it into a nested JavaScript tree. Netscape `bookmarks.html` (folders via `<DT><H3>` / links via `<DT><A>`), plus JSON / JSONL / CSV.
2. **Render** — Walks the tree and renders folders/links into the DOM. Plain HTML — no virtual DOM, no framework.
3. **Edit** — Mutations (delete, restore, move, drag-reorder, bulk, tags) update the in-memory tree, then re-render.
4. **Persist** — The tree is JSON-serialized into `localStorage` on every change.
5. **Export** — Walks the tree again and emits a fresh Netscape bookmark file (`TAGS` preserved) you can import into any browser.

There is no server, no API call, no upload at any step.

---

## 🌐 Browser Support

| Browser | Version | Status |
|---|---|---|
| Chrome / Edge / Brave | 90+ | ✅ Tested |
| Firefox | 88+ | ✅ Tested |
| Safari | 14+ | ✅ Tested |
| Opera | 76+ | ✅ Tested |
| Mobile Chrome / Safari | Latest | ✅ Tested |

Any browser that supports ES2015+ (arrow functions, `Map`, `Set`, `Promise`, `URL`) will work.

**Note on mobile drag-and-drop:** HTML5 drag-and-drop is desktop-only. On touch devices use **bulk-select + Move to…** instead — it does the same job with less friction.

---

## 🗺️ Roadmap

- [x] Bulk-select to delete or move multiple bookmarks at once
- [x] Drag-and-drop reordering of folders and links
- [x] Import formats other than `bookmarks.html` (JSON, JSONL, CSV)
- [x] Tags / labels
- [x] Duplicate detection and merge
- [x] Full offline PWA with service worker
- [ ] Two-way sync via a browser extension (Chrome/Firefox)
- [ ] Optional encryption of stored data with a passphrase
- [ ] Full-text search across history snapshots
- [ ] Folder hierarchy import from CSV path notation (`Dev/Frontend/CSS`)

Have an idea? [Open an issue](https://github.com/aanneion/bookmarkcove/issues).

---

## 🤝 Contributing

Contributions, bug reports, and feature requests are welcome.

1. Fork the repo
2. Create a branch: `git checkout -b feature/your-feature`
3. Make your changes — keep it dependency-free and single-file where possible
4. Test in Chrome, Firefox, Safari, and mobile
5. Commit: `git commit -m "Add: your feature"`
6. Push: `git push origin feature/your-feature`
7. Open a Pull Request

**Guidelines**

- No frameworks, no build tools, no runtime dependencies. The app stays a single `index.html`.
- No third-party trackers, analytics, or CDNs.
- Preserve accessibility: keyboard navigation, ARIA labels, focus styles.
- Match the existing minimalist design language.

---

## 📄 License

Released under the [MIT License](LICENSE).

You're free to use, modify, and distribute this project — personal or commercial. A link back is appreciated but not required.

---

## 👤 Author

**Abdullah Al Noman Neion**

- GitHub: [@aanneion](https://github.com/aanneion)
- Project: [github.com/aanneion/bookmarkcove](https://github.com/aanneion/bookmarkcove)
- Live: [bookmarkcove.vercel.app](https://bookmarkcove.vercel.app/)

---

<div align="center">

**Made with ❤️ by [Abdullah Al Noman Neion](https://github.com/aanneion)**

If BookmarkCove saved you some time, consider giving this repo a ⭐ — it means a lot.

</div>
