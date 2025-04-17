## WAFA News Scraper

The auto-scraper pulls articles from the Palestine Authority mouthpiece [WAFA English website](https://english.wafa.ps) and add them into a CSV file. The objective of this tool is to provide journalists monitoring the ongoing genocide and the illegal occupation in Palestine by automatically annotates the headlines. The code has been gene rated using Perlexity AI and DeepSeek. 
---

## Features

- **Scrapes the latest news (pages 1–5) from WAFA's English Latest News Page**
- **CSV Layout:** Date, Time, Headline, URL, Location, Attack Type, and Event
- **Keyword-based detection** for locations (Gaza, West Bank), attack types (e.g., airstrike, demolition, shooting), and human rights event categories (e.g., Killings, Injury, Displacement, Medical Infrastructure)
- **Deduplicates and merges** with existing CSVs
- **Configurable and extensible** keyword lists

---

## Requirements

- Python 3.7+
- `requests`
- `beautifulsoup4`
- `pandas`

Install dependencies with:

```bash
pip install requests beautifulsoup4 pandas
```

---

## Usage

1. **Clone or download this repository.**
2. **Run the scraper:**

   ```bash
   python wafa_scraper.py
   ```

3. **Output:**  
   The script creates/updates `wafa_latest_news.csv` in the current directory, containing the latest structured news data.

---

## Output CSV Fields

| Field      | Description                                                |
|------------|-----------------------------------------------------------|
| Date       | Publication date (YYYY-MM-DD)                             |
| Time       | Publication time (HH:MM:SS, if available)                 |
| Headline   | Article headline                                          |
| URL        | Full URL to the article                                   |
| Location   | "Gaza", "West Bank", or blank (based on keyword match)    |
| Attack     | Attack type (e.g., airstrike, demolition, shooting)       |
| Events     | Comma-separated event categories (e.g., Killings, Injury) |

---

## How It Works

- **Scraping:**  
  Fetches each news page (1–5) using `requests` with robust error handling and a custom user-agent.
- **Article Extraction:**  
  Uses multiple fallback HTML selectors to locate news articles, adapting to changes in site structure.
- **Data Extraction:**  
  For each article, extracts headline, summary, date/time, and URL. Uses keyword lists to detect:
    - **Location** (Gaza/West Bank)
    - **Attack Type** (e.g., airstrike, demolition, shooting)
    - **Event Categories** (e.g., Killings, Displacement, Medical Infrastructure, etc.)
- **Deduplication:**  
  Merges with existing CSV data, deduplicating by headline and date.
- **Logging:**  
  Logs all actions and errors to `wafa_scraper.log` and the console.

---

## Customization

- **Keyword Expansion:**  
  To add or modify keywords for locations, attacks, or events, edit the `GAZA_TERMS`, `WEST_BANK_TERMS`, `ATTACK_KEYWORDS`, or `EVENT_KEYWORDS` lists/dictionaries in the script.

---

## Logging

- All actions, warnings, and errors are logged to `wafa_scraper.log` and the console for transparency and troubleshooting.

---

## Limitations

- **Keyword-based detection** may miss or misclassify some events; review and expand keyword lists as needed.

---

## License

This project is released under the GNU GENERAL PUBLIC LICENSE.

---

## Contact

For questions, suggestions, or contributions, please open an issue or contact the maintainer.

---

*This tool is intended for journalistic, research, and human rights documentation purposes.*

