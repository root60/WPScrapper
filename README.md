# WPScrapper — 🕶️ Blackbox Edition

```
![HydraStrike Banner](https://raw.githubusercontent.com/RedHydra/HydraStrike/main/assets/banner.png) 
```

> **Dark UI. Clean output. Ethical intentions.**  
> A noir-styled command-line WordPress content extractor — built to pull public posts, pages, media links and metadata into tidy JSON/CSV/SQLite exports for analysis, migration, or archiving.

---

## One-line
**WPScrapper (Blackbox Edition)** — fast, configurable CLI tool to scrape public WordPress content and export structured archives.

---

## What is this?
WPScrapper is a lightweight Python command-line utility that crawls **public** WordPress sites and extracts posts, pages, media URLs, authors, categories/tags, and metadata. The README leans on a hacker-y aesthetic, but the tool is intended for legitimate use: backups, research, migration, and forensic analysis of publicly available content.

---

## ⚠️ Important — Read This First
- **Only** scrape sites you own or have explicit permission to scrape.  
- Respect `robots.txt`, server load, and site TOS.  
- Do **not** scrape private, login-protected, copyrighted, or personal data without consent.  
- Misuse can be illegal. You are responsible for how you use this software.

---

## Features
- Extract posts, pages, and custom post types (title, excerpt, content, date, slug).  
- Collect media URLs (images, embeds) and optionally download assets to a local folder.  
- Capture taxonomy data: categories, tags, and custom taxonomies.  
- Export to **JSON**, **CSV**, or **SQLite** for easy analysis.  
- CLI flags for URL, depth, rate-limiting, and output selection.  
- Modular parser architecture for site-specific tweaks.  
- Optional `--respect-robots` and `--rate-limit` to minimize impact.

---

## Installation
```bash
git clone https://github.com/yourusername/WPScrapper.git
cd WPScrapper

python -m venv venv
# On macOS / Linux
source venv/bin/activate
# On Windows
# venv\Scripts\activate

pip install -r requirements.txt
```

> Requirements: Python 3.8+ and packages listed in `requirements.txt` (e.g., `requests`, `beautifulsoup4`, `lxml`).

---

## Quick Start / Examples
Basic run (save posts to JSON):
```bash
python WPScrapper.py --url "https://example.com" --output posts.json --format json
```

Scrape depth 2, download media, export to SQLite:
```bash
python WPScrapper.py --url "https://example-blog.com" --depth 2 --download-media --output blog_archive.sqlite --format sqlite
```

Limit to 50 posts, respect robots, 2s delay between requests:
```bash
python WPScrapper.py --url "https://site.com" --limit 50 --respect-robots --rate-limit 2 --output sample.json
```

---

## CLI Flags
```
--url <site>             # target WordPress site (required)
--format <json|csv|sqlite>
--output <path>          # output filename
--depth <n>              # crawl depth (default: 1)
--download-media         # download media into ./media/
--rate-limit <seconds>   # delay between requests (default: 1)
--respect-robots         # honor robots.txt (recommended)
--limit <n>              # stop after n posts (sampling)
--concurrency <n>        # max concurrent requests (default: 1)
--help
```

---

## Output Formats
- **JSON** — nested structured export (posts, media, taxonomies).  
- **CSV** — flattened rows, best for spreadsheets.  
- **SQLite** — single-file database for queries and tooling.  
- Optional `media/` folder with downloaded assets when `--download-media` is used.

---

## Architecture (high-level)
- `WPScrapper.py` — CLI entrypoint and flow coordinator.  
- `scraper/` — site parsers and extractors.  
- `exporter/` — JSON/CSV/SQLite serializers.  
- `download/` — media downloader and asset manager.  
- `utils/` — helpers (URL normalization, rate limiter, robots check).

Drop a new parser into `scraper/` to adapt to custom WP themes and heavy-JS sites (consider server-side rendering or DOM snapshots).

---

## Ethics & Responsible Use
This README wears a black hat aesthetic, but the tool embodies white-hat rules:
- Do not attempt to bypass access controls, CAPTCHAs, or authentication.  
- Do not impersonate users or obfuscate identity for evasion.  
- Use rate limiting and `--respect-robots` to reduce impact.  
- For large-scale scraping, contact site owners and get permission.

---

## Contributing
Contributions are welcome but please keep them ethical:
- Bug fixes and test coverage.  
- Parsers for WP variants (headless WP, heavy client-side JS).  
- Exporters for other formats (Parquet, XML).  
- Improvements to throttling, retries, and error handling.

When opening PRs: include tests and ensure changes don't enable circumvention of protections.

---

## Tests
Add unit tests for parsers and exporters. Example:
```bash
pytest tests/
```

---

## Troubleshooting
- If pages are blank or JS-driven, try a headless rendering approach (not included by default).  
- If you receive HTTP 429/403 responses, increase `--rate-limit` and enable `--respect-robots`.  
- Media download errors may be due to remote hotlink protection; check headers and site policy.

---

## License
MIT License — see `LICENSE` for details. Use responsibly.

---

## A final word — Blackbox Vibe
> “Shadows don’t hide wrongdoing — they highlight what’s worth protecting.”  
> Use WPScrapper to illuminate, archive, and analyze public content — not to exploit it.

---

If you want, I can also:
- Save this as `README.md` and give you a download link.  
- Add badges, CI/coverage snippets, or ASCII art badges for a darker terminal look.  
- Generate a `setup.py` / packaging files or a sample `requirements.txt`.
