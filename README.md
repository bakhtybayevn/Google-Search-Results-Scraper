# Google Search Results Scraper
This is a Go program for scraping Google search results for a given query. It supports various Google domains, user agents, and optional proxying. You can use this tool to programmatically retrieve Google search results and extract information like URLs, titles, and descriptions.
# Installation
1. Make sure you have Go installed on your system.
2. Clone the repository to your local machine:
git clone https://github.com/bakhtybayevn/Google-Search-Results-Scraper.git
3. Change to the project directory:
cd google-search-result-scraper
4. Install the required Go dependencies using go get:
go get github.com/PuerkitoBio/goquery

# Usage
You can use this Google search scraper by calling the GoogleScraper function in your Go code. The function allows you to specify the search query, language, Google domain, proxy (optional), number of pages to scrape, results per page, and backoff time between requests.

Here's the function signature:
func GoogleScraper(searchQuery, language, countryCode string, proxyString interface{}, numPages, count, backoff int) ([]SearchResult, error)
For more details on how to use the function, refer to the Example section below.
# Configuration
1. Google Domains: The googleDomains map in the code contains various Google domains and their corresponding URLs. You can add or modify entries in this map to support additional domains.
2. User Agents: The userAgents slice contains a list of user agent strings. You can add more user agents or modify existing ones to simulate different web browsers.
# Example
Here's a simple example of how to use the GoogleScraper function to scrape Google search results:

package main

import (
    "fmt"
    "log"
)

func main() {
    res, err := GoogleScraper("mark zuckerberg", "en", "com", nil, 1, 30, 10)
    if err != nil {
        log.Println(err)
    } else {
        for _, v := range res {
            fmt.Println(v)
        }
    }
}

In this example, we search for "mark zuckerberg" in English on Google.com, scraping 30 results from 1 page with a backoff of 10 seconds between requests.
# Contributing
Feel free to contribute to this project by opening issues, suggesting improvements, or submitting pull requests.
