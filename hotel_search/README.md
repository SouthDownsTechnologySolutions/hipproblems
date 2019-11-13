# Building a Hotel Search API

When a user runs a hotel search on Hipmunk we search many partner sites simultaneously to ensure we give them the best options. In this problem, you'll build an API that queries each of our different partners and merges their results together.

# Background

Hipmunk has a scraper farm that we use to search our partner sites. The name scraper is a legacy holdover from when we actually scraped them. Nowadays, we query their APIs :)

For this problem, the scraper farm will be emulated by a simple HTTP server.

To start it, run `python -m hotel_search.scraperapi`. This should start a server listening on port 9000.

This server exposes exactly one endpoint:

- `GET /scrapers/<provider>` - returns hotel results for the specified provider as JSON

Here are the providers that are available:

- Expedia
- Orbitz
- Priceline
- Travelocity
- Hilton

# The Challenge

Your task is to build a web application for hotel search. Query each provider via HTTP, merge their results, and display the results in a UI.

Requirements:
- You must search all providers via HTTP.
- The results should be sorted by ecstasy, which represents each hotel property's aggregate value. Higher is better.
- The scraper APIs already return results sorted by ecstasy, and you should take advantage of this!

You may write your backend in whatever language you want. It should run on port 8000 and expose one HTTP endpoint:

- `GET /hotels/search` - returns hotel results from all providers as JSON

The backend response should look identical to a scraper API response except that it will contain results from all providers while still being sorted by ecstasy.

# Testing

A basic test script has been included. To use it, make sure both the scraper API and your API are running then simply run `python -m hotel_search.scraperapi_test`.
