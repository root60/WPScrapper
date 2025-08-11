<!-- Banner -->
<p align="center">
  <img src="Screenshot.PNG" alt="Mass WordPress Scrapper" width="800">
</p>

<h1 align="center" style="color:#38A169;">ðŸ•µï¸â€â™‚ï¸ Mass WordPress Scrapper</h1>
<p align="center">
  <b>Advanced discovery tool with concurrent dork & subdomain scanning for WordPress sites</b><br>
  <i>Developed by <b>RedHydra</b></i>
</p>

---

## ðŸ“œ Overview
**Mass WordPress Scrapper** is a **cross-platform** reconnaissance tool designed to discover WordPress websites with high efficiency.  
It leverages:

- **Google Dorks & DuckDuckGo search**
- **AI-powered dork generation** via Google Gemini
- **Live subdomain scanning** using DNS & HTTP checks
- **Multi-threaded and asynchronous scanning** for maximum performance  

âœ¨ Includes a **modern PyQt5 GUI** with dark theme, real-time logs, and exportable results.

---

## ðŸŽ¯ Features

âœ… **Concurrent Dork Scanning** using DuckDuckGo (`ddgs`)  
ðŸ¤– **Gemini AI Integration** for intelligent dork generation  
ðŸŒ **Advanced Subdomain Discovery** from:
- `crt.sh` certificate transparency logs
- Large built-in seed list
- WordPress-specific patterns  

ðŸ–¥ **PyQt5 GUI** with:
- Multiple tabs: Dork Generation, Results, Subdomains, Settings, Logs
- Dark theme & modern styling  

ðŸ’¾ **Exportable Results** in `.txt` and `.json`:
- `urls.txt` â€“ Found WordPress URLs
- `domains.txt` â€“ Base domains
- `subdomains.txt` â€“ WordPress subdomains
- `scan_results.json` â€“ Combined data

---

## ðŸ“· Screenshots
<p align="center">
  <img src="Screenshot.gif" alt="GUI Screenshot" width="800">
</p>

---

## ðŸš€ Installation

```bash
# Clone the repository
git clone https://github.com/root60/WPScrapper.git
cd WPScrapper

# Install dependencies
pip install ddgs aiodns aiohttp PyQt5 colorama google-generativeai
```

---

## ðŸ›  Usage

### Launch the Application
```bash
py -3 WPScrapper.py
```

### Requirements
- **Python 3.8+**
- Internet connection
- *(Optional)* Google Gemini API key for AI dork generation

---

## âš™ Configuration
- On first run, `config.json` is auto-generated.
- Configure scan settings, concurrency, and API keys via the **Settings** tab.
- Results are stored in the `results/` directory:
  - `urls.txt` â€“ WordPress URLs
  - `domains.txt` â€“ Base domains
  - `subdomains.txt` â€“ WordPress subdomains
  - `scan_results.json` â€“ Complete dataset

---

## ðŸ“Œ Notes
- Uses **DuckDuckGo** to bypass Google scraping limits.
- Subdomain enumeration is **passive** (no brute-forcing).
- Fully works on **Windows** and **Linux**  
  *(X11 required for GUI in Linux SSH sessions)*.

---

## ðŸ“„ License
Released under the **MIT License**.  
Use responsibly for **security research & educational purposes only**.

---

<p align="center">
  <sub>â­ If you like this project, consider starring it on GitHub!</sub>
</p>
