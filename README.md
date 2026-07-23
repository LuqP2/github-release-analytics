# Release Radar — GitHub Release Download Analytics

**[▶ Live app](https://luqp2.github.io/github-release-analytics/)**

Analyze the download statistics of any public GitHub repository's releases — and track how they grow **over time**, with **zero backend**, no sign-in, and nothing to host.

Everything runs client-side in a single `index.html`. Your data never leaves your browser.

---

## Why it's different

GitHub's API only exposes a **cumulative** download count — a single number per asset, with no history. Every other static release-stats tool is therefore stuck showing a one-time snapshot, and the tools that *do* show history require a backend, a login, and only start tracking after you sign up.

Release Radar solves the history problem **without a backend**:

### 📈 Velocity Engine — real download tracking, no server
Every time you analyze a repo, a timestamped snapshot is saved **locally in your browser**. Revisit later and Release Radar computes **real measured velocity** (not estimated from release dates) and plots true downloads-over-time. Export/import the history as JSON to back it up, sync across machines, or share it.

### 🟢 Per-version and per-asset growth arrows
Versions that gained downloads since your last snapshot are flagged with a green ▲ and the exact delta — so you can see at a glance which releases are still being pulled. Expand a release and the same tracking goes one level deeper: track download growth for every release asset over time, and see exactly how many new downloads each binary gained since your last visit. Assets that have gone quiet get a discreet "last seen" hint instead, showing the last window in which growth was detected.

### ⭐ Star history
See a repo's star growth as a cumulative chart, plus stats like average stars/day and the day it gained the most. Requires a token with access to the repo (GitHub restricts this data to admins/collaborators as of June 2026), so it works out of the box for your own repos.

### 🧠 Automatic insights
Most-downloaded release, dominant platform, download momentum (recent vs. older releases), and latest-version adoption — generated automatically, no configuration.

### ⚖️ Multi-repo comparison
Benchmark total downloads across several repositories side by side.

### 🗂️ Rich breakdowns & exports
Per-version, per-asset breakdown with expanded platform detection (Windows, macOS, Linux, **Android/APK**, snap, flatpak, msix, and more). Export to **CSV**, **JSON**, or **PDF**.

### 🔍 Release filter
Narrow the releases table and the download trend chart down to a search term or a date range — useful for zooming into a specific version or release window on repos with a long history.

### ✨ Premium UX
Dark / light mode, KPI cards, version adoption chart, platform split donut, recent-repo shortcuts, and `?repo=owner/repo` deep-links that auto-load.

---

## Usage

1. Open the [live app](https://luqp2.github.io/github-release-analytics/).
2. Type a repository as `owner/repo` (e.g. `ollama/ollama`) and hit **Analyze**.
3. *(Optional)* Add a GitHub Personal Access Token to raise the rate limit from 60 to 5,000 requests/hour. The token stays in memory for the session only — never stored, never sent anywhere except the GitHub API.
4. Revisit periodically — the more snapshots you accumulate, the more accurate the measured velocity.

You can also deep-link straight to a repo:

```
https://luqp2.github.io/github-release-analytics/?repo=ollama/ollama
```

---

## Privacy

- 100% client-side. No analytics, no tracking, no server.
- Snapshots are stored in your browser's `localStorage` and never leave your machine unless you explicitly export them.
- Tokens are kept in memory only and are sent exclusively to `api.github.com`.

---

## Tech

Single static `index.html` — [Chart.js](https://www.chartjs.org/) for charts and [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) for PDF export, both loaded from a CDN. No build step, deployable on any static host (GitHub Pages).

## License

MIT
