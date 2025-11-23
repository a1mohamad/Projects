# Automatic News Scraping with Python, Newspaper, and Feedparser 📰

## Project Description
This notebook provides a solution for **automatic news scraping** by extracting relevant information from online news articles. The extracted data includes the **title, author, publish date, and the main content** of the article.

The output can be used for various applications such as:
* Creating a personal news feed.
* Analyzing trends in the news.
* Building a dataset for Natural Language Processing (NLP) tasks.

---

## Technologies and Libraries
This project leverages the power of Python and two essential modules for efficient web scraping:

* **`newspaper`:** A powerful library used for **extracting and parsing** news articles from various sources, making it easy to download and analyze article content.
* **`feedparser`:** A dedicated module for parsing **RSS (Really Simple Syndication) feeds**. RSS feeds are used to find and access structured updates from websites.
* **Pandas:** For structuring the scraped data into a readable DataFrame.
* **Requests:** For handling HTTP requests to the web sources.

---

## Methodology
The scraping process follows these core steps:

1.  **Identify RSS Feed:** An RSS feed URL (e.g., from a major news source like The New York Times) is chosen as the target.
2.  **Parse the Feed:** The `feedparser` module is used to read and parse the RSS feed, which provides a list of recent article entries.
3.  **Process Articles:** The notebook iterates through each entry in the parsed feed.
4.  **Extract Full Content:** For each article link, the `newspaper` library is used to download the full HTML content and intelligently parse it to extract clean data points:
    * Article Title
    * Authors
    * Publication Date
    * The main text of the article
5.  **Output:** The extracted details are typically printed or collected into a structured format (like a Pandas DataFrame) for further analysis.

---

## References and Links
* [Automatic News Scraping with Python, Newspaper and Feedparser](https://www.geeksforgeeeks.org/automatic-news-scraping-with-python-newspaper-and-feedparser/)
* [Newspaper Documentation](https://newspaper.readthedocs.io/en/latest/)
* [Finding an RSS Feed URL](https://help.socialbee.com/article/78-how-can-i-find-the-rss-feed-of-a-website#feed)