# Google Maps Business Scraper

Skip pricey Chrome extensions—scrape unlimited Google Business data for free with this script. Instead of paying recurring fees, run a customizable Playwright-based scraper on your own machine to export JSON, CSV, and Excel files in one go.

| Feature / Cost | Paid Chrome Extension | This Script |
| --- | --- | --- |
| Monthly price | \$49–\$199+ | \$0 |
| Data limits | Tiered quotas | Unlimited (your hardware + patience) |
| Export formats | CSV only (often) | JSON, CSV, XLSX |
| Custom queries | Limited UI | Fully editable `queries` list |
| Browser visibility | Headless only | Interactive Chromium window |
| Ownership | Vendor controlled | You own the code/data |

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
3. Update the `queries` list in `script.py` to change search terms—just edit the array of strings, for example:
   ```python
   queries = [
       "Dentist Austin TX",
       "Chiropractor Austin TX",
   ]
   ```
   The scraper runs once for each string and pulls every matching Google Maps business.
4. Run the scraper:
   ```bash
   python script.py
   ```
5. Generated files appear next to the script (`.json`, `.csv`, `.xlsx`). They remain local because the directories are ignored by git.

## Notes

- The scraper launches Chromium in non-headless mode; you can change `headless=False` in `scrape_businesses` if you prefer headless runs.
- Respect Google’s Terms of Service and relevant laws when scraping search results.

