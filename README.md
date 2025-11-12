# Google Maps Business Scraper

This project contains an asynchronous Google Maps scraper that collects business details for a list of search queries and writes the results to JSON, CSV, and Excel files.

- **Script entry point:** `script.py`
- **Output formats:** JSON, CSV, XLSX (now ignored by git; generated locally)
- **Tech stack:** Python, Playwright, OpenPyXL

## Prerequisites

- Python 3.10+
- Google Chrome/Chromium installed locally
- Ability to install Python packages and Playwright browser binaries

## Quick Start

1. Create and activate a virtual environment:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```
2. Install dependencies and the Playwright browser:
   ```bash
   pip install --upgrade pip
   pip install playwright openpyxl
   playwright install chromium
   ```
3. Update the `queries` list in `script.py` if you want different search terms.
4. Run the scraper:
   ```bash
   python script.py
   ```
5. Generated files appear next to the script (`.json`, `.csv`, `.xlsx`). They remain local because the directories are ignored by git.

## Notes

- The scraper launches Chromium in non-headless mode; you can change `headless=False` in `scrape_businesses` if you prefer headless runs.
- Respect Google’s Terms of Service and relevant laws when scraping search results.

