Great! Here's a complete learning guide for **Web Scraping with Python (10 Hours)** with **examples** for each topic:

---

## 🌐 1. Introduction to Web Scraping

**Web scraping** means extracting data from websites using tools or scripts.

> Legal Note: Always check a website’s `robots.txt` file and Terms of Use.

### Example: Fetching Web Page HTML

```python
import requests

url = "https://example.com"
response = requests.get(url)

print("Status Code:", response.status_code)
print("HTML Content:\n", response.text[:500])
```

---

## 🔍 2. Regular Expressions (RegEx)

Used to match patterns in text (e.g., emails, phone numbers).

### Example: Match Email Addresses

```python
import re

text = "Contact us at support@example.com or sales@example.org"
emails = re.findall(r"[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}", text)
print("Found emails:", emails)
```

---

## 🥣 3. BeautifulSoup (HTML/XML Parsing)

### Install:
```bash
pip install beautifulsoup4 requests
```

### Example: Extract Titles from a Page

```python
import requests
from bs4 import BeautifulSoup

url = "https://example.com"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

print("Title:", soup.title.string)
```

### Example: Extract All Links

```python
for link in soup.find_all('a'):
    print(link.get('href'))
```

---

## 🎮 4. Selenium (Interact with JavaScript content)

### Install:
```bash
pip install selenium
```

### Setup WebDriver (e.g., Chrome):
```bash
# Download ChromeDriver and ensure it matches your browser version.
# https://chromedriver.chromium.org/downloads
```

### Example: Open Page and Click

```python
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()
driver.get("https://example.com")

# Example: Get title
print("Page Title:", driver.title)

# Click a button (if exists)
# driver.find_element(By.ID, "submit-button").click()

driver.quit()
```

---

## 🕷️ 5. Scrapy (For Large-Scale Crawling)

### Install:
```bash
pip install scrapy
```

### Create Project:
```bash
scrapy startproject myproject
cd myproject
```

### Example Spider (`myproject/spiders/example.py`):

```python
import scrapy

class ExampleSpider(scrapy.Spider):
    name = "example"
    start_urls = ["https://quotes.toscrape.com"]

    def parse(self, response):
        for quote in response.css("div.quote"):
            yield {
                'text': quote.css("span.text::text").get(),
                'author': quote.css("small.author::text").get(),
            }
```

### Run Spider:
```bash
scrapy crawl example
```

---

## 🔧 Web Scraping Project Examples

### ✅ Project 1: Scrape Book Titles from a Website

```python
import requests
from bs4 import BeautifulSoup

url = "http://books.toscrape.com"
res = requests.get(url)
soup = BeautifulSoup(res.text, 'html.parser')

titles = [book.get('title') for book in soup.select('h3 a')]
print("Book Titles:", titles)
```

---

### ✅ Project 2: Scrape Live Weather from Website

```python
import requests
from bs4 import BeautifulSoup

url = "https://www.weather-forecast.com/locations/London/forecasts/latest"
res = requests.get(url)
soup = BeautifulSoup(res.text, 'html.parser')

forecast = soup.find('span', class_='phrase')
print("Forecast:", forecast.text if forecast else "Not found")
```

---

### ✅ Project 3: Dynamic Website Scraping with Selenium

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()
driver.get("https://quotes.toscrape.com/js")

time.sleep(3)  # Let JavaScript render

quotes = driver.find_elements(By.CLASS_NAME, "text")
for quote in quotes:
    print(quote.text)

driver.quit()
```

---

### ✅ Project 4: Crawl Multiple Pages with Scrapy

```python
def parse(self, response):
    for quote in response.css("div.quote"):
        yield {
            'text': quote.css("span.text::text").get(),
            'author': quote.css("small.author::text").get()
        }
    
    next_page = response.css("li.next a::attr(href)").get()
    if next_page:
        yield response.follow(next_page, self.parse)
```

---

Would you like to build a complete mini-project (e.g., job listing scraper or e-commerce price tracker)? I can guide you through that step-by-step!