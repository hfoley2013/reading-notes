# Web Scraping

## Reading

* [Web Scrape with Python in 4 minutes](https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460)
* [What is Web Scraping?](https://en.wikipedia.org/wiki/Web_scraping)
* [How to scrape websites without getting blocked]](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)
* [Video: Track Amazon Prices](https://www.youtube.com/watch?v=Bg9r_yLk7VY)

## References

* [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/)

## Notes

### Web Scraping with Python

Web scraping is the process of extracting data from websites. It involves making HTTP requests to a website's server, downloading the HTML of the web page, and then parsing that HTML to extract the data you need. Web scraping allows you to automate the process of data collection from websites, making it possible to extract large amounts of data quickly and efficiently. It can be used for a wide range of applications, such as data mining, data analysis, and information monitoring.

There are a few reasons why websites may try to block web scraping:

* To protect their data: Some websites may have proprietary data that they don't want others to access and use without permission.
* To prevent excessive traffic: Web scraping can generate a lot of traffic, and if a website is not designed to handle a large number of requests, it can cause the server to crash or become slow.
* To prevent fraud: Web scrapers can sometimes be used to commit fraud, such as by scraping credit card numbers or personal information from e-commerce websites.
* To maintain the integrity of the website: Web scrapers can sometimes inadvertently break a website by making a large number of requests in a short period of time, or by not following the website's robots.txt file, which specifies rules for web crawlers.

In general, it is important to respect a website's terms of service and to obtain permission before scraping data from it.

### Ethical Web Scraping

* Respect Robots.txt
  * `Robots.txt` has rules for crawlers such as how frequently yu can scrape, which pages allow scraping, etc.
  * Usually located at the root directory of the site: `https://examples.com/robots.txt`
  * If it contains `User-agent: *` or `Disallow:/` it means the site does not want to be scraped
* Make the crawling slower, do not slam the server, treat websites nicely
  * Ideally a delay of 10-20 seconds
* Do not follow the same crawling pattern
  * Incorporate some random clicks on the page, mouse movements and random actions that will make a spider look like a human.
* Make requests through Proxies and rotate them as needed
  * Rotate out your IP with TOR, VPNs, Proxies, etc.
* Rotate User Agents and corresponding HTTP Request Headers between requests
* Use a headless browser like Puppeteer, Selenium or Playwright
* Beware of Honey Pot Traps
* Check if Website is Changing Layouts
* Avoid scraping data behind a login
* Use Captcha Solving Services

#### Giveaways that your are a scraper (and making the website hate you)

* Scraping too fast and too many pages, faster than a human ever can
* Following the same pattern while crawling. For example – go through all pages of search results, and go to each result only after grabbing links to them. No human ever does that.
* Too many requests from the same IP address in a very short time
* Not identifying as a popular browser. You can do this by specifying a ‘User-Agent’.
* Using a user agent string of a very old browser

#### Web Scraping Techniques

* **HTML parsing:** This involves using a library like Beautiful Soup to parse the HTML of a web page and extract the data you need.
* **HTTP libraries:** You can use a library like requests to make HTTP requests to a website and then parse the HTML response to extract the data you need.
* **Headless browsers:** A headless browser is a web browser that runs without a GUI, making it easier to automate web scraping tasks. You can use a headless browser like Puppeteer to control a web browser through code and scrape websites.
* **APIs:** Some websites provide APIs that allow you to retrieve data in a structured format. Using an API can be a more efficient way to scrape data, as it eliminates the need to parse HTML.
* **Web scraping frameworks:** There are several frameworks that have been developed specifically for web scraping, such as Scrapy and PySpider. These frameworks can make it easier to build and maintain web scrapers.
