<!-- Banner -->
<p align="center">
  <img src="Screenshot.PNG" alt="GUI Screenshot" width="800"/>
</p>

<h1 align="center" style="color:#38A169;">Mass WordPress Scrapper v2</h1>
<p align="center">
  <b>A deeply enhanced discovery and reconnaissance tool with concurrent dork & subdomain scanning for WordPress sites.</b><br>
  <i>Developed by RedHydra</i>
</p>

---

## 📜 Overview

**Mass WordPress Scrapper v2** is a powerful, cross-platform tool designed for penetration testers and security researchers to discover and analyze WordPress websites on a massive scale. Version 2 moves beyond simple discovery, incorporating a deep analysis engine to scrape valuable intelligence from target sites.

It automates reconnaissance by combining high-speed dorking, AI-powered query generation, and extensive subdomain enumeration with detailed site analysis to uncover versions, plugins, themes, exposed files, and potential misconfigurations.

---

## ✨ v2 Key Enhancements

- **Deep Site Analysis**: Now scrapes for WP Version, REST API endpoints, user info via author enumeration, exposed backup files, and common plugins/themes.
- **Vastly Expanded Discovery**: Fetches 4x more results per dork and scans over 100 common subdomains per domain (up from 10).
- **Functional AI Dorking**: The previously non-functional Gemini AI feature is now fully implemented and fixed, allowing you to generate hundreds of creative dorks.
- **Performance Tuning**: Default settings have been optimized for faster, more aggressive scanning.

---

## 🎯 Core Features

- 🔍 **Concurrent Dork Scanning**: Uses `asyncio` and DuckDuckGo to process a huge number of dorks with incredible speed.
- 🤖 **Gemini AI Integration**: Provide an API key to automatically generate hundreds of unique, high-quality dorks based on your keywords.
- 🌐 **Advanced Subdomain Discovery**: Finds potential targets through `crt.sh` certificate logs and an expanded built-in seed list.
- 🕵️ **Detailed Reconnaissance**: Probes each discovered site to identify:
    - WordPress Version
    - Exposed Endpoints (`wp-json`, `xmlrpc`, etc.)
    - Publicly accessible files (`readme.html`, `license.txt`, backups)
    - Usernames (via author enumeration)
    - Hints of installed Plugins & Themes
- 🖥️ **Modern PyQt5 GUI**: A sleek, user-friendly interface with a dark theme, real-time logging, and organized results.
- 💾 **Exportable Results**: Save all found URLs, domains, and detailed subdomain analysis to `.txt` and `.json` files.

---

## 📷 Screenshot

<p align="center">
  <img src="Screenshot.gif" alt="GUI Demo"/>
</p>

---

## 🚀 Installation

The tool is cross-platform. Follow the instructions for your operating system.

**Prerequisites:**
- Python 3.8+
- Git

### 🐧 Linux (Debian/Ubuntu, Kali Linux)
```bash
# Update package list and install dependencies
sudo apt update && sudo apt install git python3-pip python3-venv -y

# Clone the repository
git clone https://github.com/root60/WPScrapper.git
cd WPScrapper

# Create and activate a virtual environment
python3 -m venv venv
source venv/bin/activate

# Install required Python packages
pip install ddgs aiodns aiohttp PyQt5 colorama google-generativeai
```

### 🪟 Windows
```powershell
# Clone the repository using Git Bash or another git client
git clone https://github.com/root60/WPScrapper.git
cd WPScrapper

# Create and activate a virtual environment
python -m venv venv
.\venv\Scripts\activate

# Install required Python packages
pip install ddgs aiodns aiohttp PyQt5 colorama google-generativeai
```

---

## 🛠 Usage

### 🖥️ GUI Mode (Recommended)
This is the primary way to use the tool, giving you access to all features.

1.  **Run the application:**
    ```bash
    # On Linux
    python3 WPScrapper.py
    
    # On Windows
    python WPScrapper.py
    ```
2.  **Generate Dorks:**
    - Navigate to the **"Dork Generation"** tab.
    - Enter keywords into the "Keywords" box (e.g., `real estate`, `local business`, `online store`).
    - **(Optional for AI)** Go to the **Settings** tab, add your Google Gemini API key, and check "Use Gemini..."
    - Click **"Generate Dorks"**. The preview box will fill with standard and (if enabled) AI-generated dorks.
3.  **Start the Scan:**
    - Click the **"Start Scan"** button.
    - Monitor progress in the **Activity Log** tab and see live results populate in the **Results** and **Subdomains** tabs.

### ⌨️ CLI Mode
The script automatically falls back to a command-line interface if `PyQt5` is not installed, making it ideal for servers or headless systems.
- Run the script as above.
- It will prompt you to enter keywords one by one. Press Enter on an empty line to start the scan.

---

## ✅ Professional & Ethical Applications

This tool is designed for legitimate cybersecurity work. Using the scraped data responsibly can lead to professional growth and rewards.

#### Cybersecurity Services (Penetration Testing)
As a penetration tester or security consultant, you can use this tool during the initial reconnaissance phase of an engagement. The information gathered—such as software versions, plugins, and exposed subdomains—is critical for identifying potential attack vectors on behalf of a client **who has given you explicit, written permission** to assess their systems.

#### Authorized Bug Bounty Programs
Many companies offer bug bounty programs (e.g., on platforms like HackerOne or Bugcrowd) where they reward researchers for finding and reporting vulnerabilities. You can use this tool to find assets that are in-scope for such a program and analyze them for bugs. This is a legitimate way to earn money and build a professional reputation.

#### Security Research
The data can be used to analyze the prevalence of certain WordPress versions, plugins, or themes across the web. This can help in identifying widespread vulnerabilities (e.g., a zero-day in a popular plugin) and responsibly disclosing them to vendors or the public, contributing to a safer internet for everyone.

#### Market & Competitive Analysis (Use with Extreme Caution)
While the tool can identify sites in a specific niche (e.g., "real estate sites using WooCommerce"), this application borders on unsolicited data scraping. **You must respect `robots.txt` files, website Terms of Service, and data privacy laws like GDPR and CCPA.** Misuse can have serious legal consequences. This is not the primary intended use of the tool.

---

## ⚙ Configuration
- On first run, a `config.json` is generated.
- Scan settings, concurrency, and API keys can be modified from the **Settings** tab in the GUI or by editing the file directly.
- All results are saved in the `results/` directory for persistence and analysis.

---

## ⚠️ Disclaimer & Responsible Use
This project is released under the **MIT License**.

The developer is not responsible for any misuse of this tool. It is intended for **educational and ethical security research purposes only**. Unauthorized scanning of websites is illegal. Always ensure you have explicit, written permission from the owner of any system before performing any security testing.
