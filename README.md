## WAFA News Scraper

This tool automatically scrapes news headlines from [WAFA English website](https://english.wafa.ps) — the official Palestinian Authority news agency — and annotates them by location, attack type, and event category. The output is a CSV file designed for journalists and researchers monitoring the ongoing situation in Palestine. The project includes ready-to-use scripts for generating summary tables and charts.

---

### Features

- **Scrapes latest headlines (pages 1–5) from WAFA**
- **Exports to CSV:** Date, Time, Headline, URL, Location, Attack, Events
- **Auto-annotates** with keywords for location, attack type, and human rights event category
- **Deduplicates** and merges with existing CSVs

---

### Quickstart

1. **Install requirements:**
   ```bash
   pip install requests beautifulsoup4 pandas
   ```

2. **Run the scraper:**
   ```bash
   python wafa_scraper.py
   ```

3. **Generate summary tables and charts:**
   ```bash
   python wafa_summary.py
   ```

   - This will print pretty tables and show charts for Location, Attack, and Events.

---

### CSV Fields

| Field    | Description                                    |
|----------|------------------------------------------------|
| Date     | Publication date (YYYY-MM-DD)                  |
| Time     | Publication time (if available)                |
| Headline | Article headline                               |
| URL      | Full article link                              |
| Location | Gaza, West Bank, or Not Coded                  |
| Attack   | Attack type (e.g., airstrike, demolition, etc) |
| Events   | Event categories (e.g., Killings, Injury, ...) |

---

### Customization

To add or change keywords for annotation, edit the `GAZA_TERMS`, `WEST_BANK_TERMS`, `ATTACK_KEYWORDS`, or `EVENT_KEYWORDS` lists in the script.

---

### License

GNU GENERAL PUBLIC LICENSE

---

*For questions or contributions, open an issue or contact the maintainer.*

---

**This tool is for journalistic, research, and human rights documentation.**

