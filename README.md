# C++ Web Crawler

A C++-based application that recursively traverses web pages, extracts URLs from the HTML content, and crawls through them. This project uses cURL for HTTP requests and `regex` for extracting links. It allows for customizable crawling depth and is lightweight, making it a simple tool for web scraping.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Limitations](#limitations)
- [Future Improvements](#future-improvements)

## Overview

This project is designed to crawl through web pages starting from a given URL. It extracts all the URLs from the HTML content of the webpage and recursively follows these URLs up to a specified depth. The application is simple and performs well for basic web crawling tasks.

## Features

- **HTTP GET Requests**: Uses cURL to fetch HTML content from a given URL.
- **URL Extraction**: Employs regular expressions to extract links from HTML.
- **Recursive Crawling**: Follows extracted URLs up to a user-defined depth.
- **Lightweight Implementation**: Focused on simplicity and ease of use.

## Tech Stack

- **C++**: The core programming language used for development.
- **cURL**: Utilized for performing HTTP requests.
- **Regular Expressions**: Used for parsing HTML content and extracting URLs.

### Why This Tech Stack?

- **C++**: Provides performance and control over system-level tasks.
- **cURL**: Robust library for handling HTTP requests in C++.
- **Regex**: A powerful tool for extracting URLs from HTML content.

## Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/yourusername/cpp-web-crawler.git
    ```
2. Navigate to the project directory:
    ```bash
    cd cpp-web-crawler
    ```
3. Ensure that `libcurl` is installed on your system:

   On Linux:
   ```bash
   sudo apt-get install libcurl4-openssl-dev
   ```
   On macOS:

   ```bash
   brew install curl

   ````
   
## Usage

Edit the main function to specify the starting URL and the maximum depth for crawling:

```cpp
string startingURL = "https://example.com"; // Define the starting URL
int maxDepth = 1; // Define how deep the crawler should traverse
```

Compile the project:

```bash
g++ -o web_crawler web_crawler.cpp -lcurl
```

Run the application:
```bash
./web_crawler
```
The output will display the found URLs at each depth level.

## How It Works
The application performs the following steps:

- **Fetch HTML Content**: Using cURL, the program sends an HTTP GET request to retrieve the HTML content of the given URL.
- **Extract URLs**: A regular expression is used to search for `<a href="...">` tags within the HTML content, extracting the links.
- **Recursive Crawling**: The extracted URLs are recursively crawled up to the specified depth, with each URL’s HTML content retrieved and further URLs extracted.
  
## Limitations
- **No Relative URLs**: This implementation does not handle relative URLs like /about, only absolute URLs.
- **No JavaScript Support**: It cannot handle dynamic pages that load content via JavaScript.
- **Single-threaded**: The current implementation does not utilize multithreading, limiting its performance when crawling many pages.

## Future Improvements
- **Add Support for Relative URLs**: Enhance the crawler to resolve and follow relative URLs.
- **Multi-threading**: Implement multi-threading to improve performance when crawling multiple URLs.
- **Handle Dynamic Pages**: Add support for handling pages that load content via JavaScript.
- **Avoid Duplicate Crawls**: Keep track of already visited URLs to prevent crawling the same URL multiple times.
