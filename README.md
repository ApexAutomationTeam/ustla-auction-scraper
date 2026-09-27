# ustla-auction-scraper
High-performance in-browser automation tool &amp; UI control panel for scraping real estate tax deed auction data from ULS (ustla.com). Custom-tailored by Apex Automation Team.

# 🏛️ USTLA Auction Scraper & Research Automator

> 💡 **Community Project**: This tool was engineered and provided for free as part of the automation initiatives by **[Apex Automation Team](https://apexautomationteam.com/)**. Explore our portfolio for enterprise data mining, custom scraping pipelines, and workflow automations!

A specialized browser automation suite designed for extracting US Tax Deed & Auction datasets directly from the **[ULS Research Portal](https://uls.ustla.com/)** into multi-sheet formatted `.xlsx` workbooks and backup `.csv` files[cite: 17, 18, 19].

---

## 📌 Scope & Customization Note

> **Client Specification Notice**:  
> This script was originally architected according to a specific client brief. By default, it filters for **Deed** and **Redeemable Deed** auctions starting from **09/01/2025 onwards**, excluding Liens[cite: 18, 19].  
> 
> **For Developers**:  
> The codebase is fully modular. Any developer can adjust or remove these constraints to extract **all historical/future leads** across all auction types (including tax liens, foreclosures, and arbitrary date brackets) simply by adjusting the query builder payload in `listQuery()` or toggling filters via the built-in UI[cite: 18, 19].

---

## 📺 Video Demos & Release Assets

Video walkthroughs and setup guides are hosted in our official release section:

* 📦 **[View Official Release & Video Assets](https://github.com/ApexAutomationTeam/ustla-auction-scraper/releases/download/v2.3.4/USTLA.mp4)**
* 📥 Download the video demonstrations directly from the release page to see real-time execution, control panel operation, and Excel export formatting[cite: 14].

---

## 📂 Repository Contents

| File | Type | Description |
| :--- | :--- | :--- |
| `USTLA_Scraper_Panel.js` | **UI Version (Recommended)** | Spawns an interactive draggable overlay panel directly on the webpage with real-time controls, pagination ranges, and live metrics[cite: 17, 18]. |
| `USTLA_scraper_FINAL.js` | **Headless Console Version** | Raw background script for headless command-line-style execution via DevTools Console[cite: 17, 19]. |
| `README.md` | **Documentation** | Operational guide, parameter references, and troubleshooting. |

---

## 🚀 Key Features

* **Interactive Control Panel (`USTLA_Scraper_Panel.js`)**:
  * Draggable HUD with live progress bars for list discovery and detail hydration[cite: 18].
  * Single-button toggle: **Start / Pause / Resume**[cite: 17, 18].
  * Page selection: Process **All Pages** or restrict execution using **From / To** bounds[cite: 17, 18].
* **State Persistence & Fault Tolerance**:
  * Saves active state to `localStorage` / `sessionStorage`[cite: 17, 18, 19].
  * Browser crash or tab refresh protection: paste the script again and hit **Resume** to continue precisely where it stopped[cite: 17, 18].
* **Rate-Limit (HTTP 429) Auto-Backoff**:
  * Built-in intelligent jitter and backoff algorithms prevent account bans and bypass server throttling smoothly[cite: 18, 19].
* **Data Integrity Cross-Validation**:
  * Verifies list-level records against granular detail endpoints on every item to catch data mismatches[cite: 17, 18, 19].
* **Automated Excel (.xlsx) Structuring**:
  * Generates separate monthly worksheets (e.g., `Sep 2025`, `Oct 2025` ... `Dec 2026`)[cite: 18, 19].
  * Generates an automated **Progress** summary sheet with dynamic formulas (`COUNTA`, `SUM`) tracking parcel counts and aggregate sales totals[cite: 18, 19].
  * Auto-downloads a fail-safe UTF-8 `.csv` backup alongside the workbook[cite: 17, 18, 19].

---

## 📊 Extracted Data Columns (17 Standard Fields)

The scraper compiles the following structured data points for each auction listing[cite: 18, 19]:

1. `County`[cite: 18, 19]
2. `State`[cite: 18, 19]
3. `Sale Start Date`[cite: 18, 19]
4. `Start Time`[cite: 18, 19]
5. `Sale End Time`[cite: 18, 19]
6. `Bid Award Date`[cite: 18, 19]
7. `Sale Duration`[cite: 18, 19]
8. `Sale Address`[cite: 18, 19]
9. `Contact / Current Treasurer`[cite: 18, 19]
10. `Phone #`[cite: 18, 19]
11. `Fax #`[cite: 18, 19]
12. `Email`[cite: 18, 19]
13. `Number of Parcels`[cite: 18, 19]
14. `Aggregate Sale Amount`[cite: 18, 19]
15. `Bid Procedures`[cite: 18, 19]
16. `Auction Type`[cite: 18, 19]
17. `Web Address` (Direct Online Auction URL)[cite: 18, 19]

---

## 🛠️ Step-by-Step Usage Guide

### Method 1: Using the Control Panel (Recommended)

1. Open Google Chrome and log into your account at:  
   `https://uls.ustla.com/research/auctions`[cite: 18, 19]
2. Open DevTools by pressing **`F12`** (or `Right-Click` → `Inspect`) and navigate to the **Console** tab[cite: 17, 18].
3. Copy the full contents of `USTLA_Scraper_Panel.js`, paste it into the console, and press **Enter**[cite: 17, 18].
4. An interface will appear in the top-right corner[cite: 17, 18]:
   * Select your target auction types (Deed, Redeemable Deed, Lien)[cite: 18].
   * Select page ranges or check **Saari pages (all)**[cite: 18].
   * Click **▶ Start**[cite: 18].
5. Once data harvesting completes, the `.xlsx` and backup `.csv` will trigger download automatically (or via the **⬇ Download** button)[cite: 18].

### Method 2: Headless Execution

1. Navigate to the logged-in research portal[cite: 18, 19].
2. Open the browser console (`F12`), paste the contents of `USTLA_scraper_FINAL.js`, and press **Enter**[cite: 17, 19].
3. The scraper will automatically extract records in the background and output progress in the console logs[cite: 19].

---

## ⚙️ Safe Concurrency & Throttling Guidelines

> ⚠️ **Warning on Rate Limits (HTTP 429)**:  
> Running aggressive parallel requests on `uls.ustla.com` will trigger server-side IP blocks[cite: 17, 18].  
> * Keep **Concurrency** at **`2` to `3`**[cite: 17, 18].
> * Maintain a **Speed (Pace)** of at least **`300+ ms`** between requests during high-volume extractions to remain undetected and avoid throttling[cite: 17].

---

## 🏢 About Apex Automation Team

We build custom integrations, web scrapers, automated workflows, and AI solutions to scale your business operations.

* **Official Website:** [https://apexautomationteam.com/](https://apexautomationteam.com/)
* **Inquiries & Custom Tool Development:** Reach out through our portal for custom scrapers, Google Workspace tools, and data workflows.
