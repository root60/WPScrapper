<!-- Banner -->
![GUI Screenshot](Screenshot.PNG)

<h1 align="center" style="color:#38A169;">Mass WordPress Scrapper</h1>
<p align="center">
  <b>An advanced discovery tool with concurrent dork & subdomain scanning for WordPress sites.</b><br>
  <i>Developed by RedHydra</i>
</p>

---

## 📜 Overview

**Mass WordPress Scrapper** is a cross-platform tool for discovering WordPress websites using:
- **Google Dorks & DuckDuckGo search**
- **AI-powered dork generation** with Google Gemini
- **Live subdomain scanning** with DNS & HTTP checks
- **Multi-threaded and asynchronous scanning** for high performance

It includes a **modern PyQt5 GUI** with dark theme support, real-time logs, and exportable results.

---

## 🎯 Features

- 🔍 **Concurrent Dork Scanning** using DuckDuckGo (`ddgs`)
- 🤖 **Gemini AI Integration** for generating custom dorks
- 🌐 **Advanced Subdomain Discovery** from:
  - `crt.sh` certificate transparency logs
  - Built-in large seed list
  - WordPress-specific patterns
- 🖥 **PyQt5 GUI** with:
  - Tabs for dork generation, results, subdomains, settings, logs
  - Dark theme & modern styling
- 💾 **Exportable Results** (URLs, Domains, Subdomains in `.txt` and `.json`)

---

## 📷 Screenshot

![GUI Screenshot](Screenshot.gif)

---

## 🚀 Installation

```bash
# Clone the repository
git clone https://github.com/root60/WPScrapper.git
cd WPScrapper

# Install dependencies
pip -3 install ddgs aiodns aiohttp PyQt5 colorama google-generativeai
```

---

## 🛠 Usage

### Run the Application
```bash
py -3 WPScrapper.py
```

### Requirements
- Python 3.8+
- Internet connection
- Optional: Google Gemini API key for AI dork generation

---

## ⚙ Configuration
- On first run, a `config.json` file will be generated.
- Change scan settings, concurrency, and API keys from the **Settings** tab.
- Results are saved in the `results/` directory:
  - `urls.txt` – Found WordPress URLs
  - `domains.txt` – Base domains
  - `subdomains.txt` – WordPress subdomains
  - `scan_results.json` – Combined data

---

## 📌 Notes
- The scanner uses **DuckDuckGo** to avoid Google’s strict scraping limits.
- Subdomain enumeration is **passive** (no brute-forcing) for safety.
- Works on **Windows** and **Linux** (X11 required for GUI in Linux SSH sessions).

---

## 📄 License
This project is released under the **MIT License**.  
Use responsibly for security research & educational purposes only.

---

<p align="center">
