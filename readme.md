# 📧 scraper-4-email

**scraper-4-email** is a Python tool that extracts email addresses — including obfuscated formats (e.g., `[at]`, `(dot)`, `{at}`, etc.) — from websites listed in an Excel file. It retrieves pages from each site's sitemap, scrapes the content, and outputs all found emails into a clean CSV file.

---

## 📦 Installation

### From PyPI (recommended)

> Requires Python 3.7 or higher.

```bash
pip install scraper-4-email
```

### From GitHub (latest development version)

```bash
pip install git+https://github.com/kirilinko/scraper-4-email.git
```

## 🖥️ Command Line Usage

Once installed, the tool can be used directly from your terminal:

```bash
scraper-4-email path/to/sites.xlsx output.csv
```

### ✅ Example

```bash
scraper-4-email site_list.xlsx scraped_emails.csv
```

### 📥 Excel Input Format

The Excel file must contain a column named `site`, with each row containing a domain name (no protocol required):

| site            |
|-----------------|
| example.com     |
| mycompany.org   |

### 📤 CSV Output Format

The resulting CSV will contain:

| site                | pages_explored | emails                           |
|---------------------|----------------|-----------------------------------|
| https://example.com | 7              | info@example.com, contact@...    |

---

## 🐍 Usage in Python

You can also use `scraper-4-email` as a Python module in your own scripts:

```python
from scraper_4_email import run_scraper

run_scraper("site_list.xlsx", "output_emails.csv")
```

### Example Script

```python
# my_scraper_script.py

from scraper_4_email import run_scraper

input_file = "sites.xlsx"
output_file = "emails_found.csv"

run_scraper(input_file, output_file)
```

Run the script:

```bash
python my_scraper_script.py
```

---

## What It Does

- Loads domain names from an Excel `.xlsx` file
- Automatically retrieves each site's sitemap (`/page-sitemap.xml`)
- Filters out blog/news URLs to reduce noise
- Scrapes the visible text of each page
- Extracts emails using smart regex matching
- Normalizes obfuscated email formats like:
  - `john [at] example [dot] com`
  - `jane(at)company(dot)org`
  - `support {at} domain.com`
- Outputs a CSV with all detected addresses per site

## 👤 Author

Developed by **Franck D**  
📧 Email: contact@algo-mania.com  
🔗 GitHub: [github.com/kirilinko](https://github.com/kirilinko)
