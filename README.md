# Web Scraping Data Aggregator

A robust Python-based web scraping pipeline that extracts news and financial data from multiple websites and stores it in structured JSON format for easy access and analysis.

## Features

- **Multi-website scraping**: Extracts data from multiple news and financial sources simultaneously
- **Dynamic content handling**: Uses Selenium to render and scrape JavaScript-heavy websites
- **Data parsing & cleaning**: Implements BeautifulSoup for efficient HTML parsing and data extraction
- **Structured output**: Stores scraped data in JSON format with proper schema validation
- **Error handling**: Graceful error handling and logging for failed requests
- **Rate limiting**: Respects website policies with configurable delays between requests

## Tech Stack

- **Scrapy**: High-performance web scraping framework
- **Selenium**: Browser automation for dynamic content rendering
- **BeautifulSoup**: HTML/XML parsing and data extraction
- **Python 3.8+**: Core language

## Project Structure

```
WebScrapingDataAggregator/
├── scrapers/
│   ├── news_scraper.py
│   ├── financial_scraper.py
│   └── base_scraper.py
├── data/
│   └── output/
│       └── *.json
├── config.py
├── requirements.txt
└── README.md
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/harshhkalia/WebScrapingDataAggregator.git
cd WebScrapingDataAggregator
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Download ChromeDriver (for Selenium):
- Download from [ChromeDriver](https://chromedriver.chromium.org/)
- Add to your system PATH or specify path in config

## Usage

Run the scraper:
```bash
python main.py
```

Or run specific scrapers:
```bash
python scrapers/news_scraper.py
python scrapers/financial_scraper.py
```

Scraped data will be saved to `data/output/` in JSON format.

## Configuration

Edit `config.py` to customize:
- Target websites
- Request headers and user agents
- Output file locations
- Rate limiting delays
- Logging preferences

## Output Format

Data is stored in JSON with the following structure:
```json
{
  "source": "website_name",
  "title": "Article Title",
  "url": "https://example.com/article",
  "published_date": "2025-01-15",
  "content": "Article content here...",
  "category": "news|financial",
  "scraped_at": "2025-01-15T10:30:00Z"
}
```

## Key Implementation Details

- **Scrapy Spiders**: Efficient asynchronous requests for multiple websites
- **Selenium Integration**: Handles JavaScript-rendered content dynamically
- **BeautifulSoup Parsing**: Extracts specific data fields from HTML
- **Error Handling**: Logs failed requests and continues execution
- **Data Validation**: Ensures clean, structured output

## Challenges Solved

- Handling dynamic JavaScript-rendered content using Selenium
- Managing rate limiting to avoid IP blocking
- Parsing inconsistent HTML structures across different websites
- Storing and organizing large volumes of scraped data

## Future Enhancements

- Database integration (MongoDB/PostgreSQL)
- Web dashboard for data visualization
- Real-time scraping scheduler
- API endpoint for accessing scraped data
- Machine learning for content categorization

## Legal & Ethical Notice

This tool is for educational purposes. Always respect website Terms of Service and `robots.txt` policies. Ensure you have permission before scraping any website.

## License

MIT License - feel free to use this project for learning and development purposes.

## Author

Harsh Kalia - [GitHub](https://github.com/harshhkalia) | [Email](mailto:kaliaharsh24@gmail.com)

---

*Last updated: January 2025*
