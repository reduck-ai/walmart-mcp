# Search Walmart products

Automatically search Walmart products on walmart.com. Search Walmart.com by free-text query and return one page of results. Returns query, page, sort, url, total_count, max_page, corrected_query, items and related_items (each item: us_item_id, name, url, price, was_price, unit_price, rating, review_count, image_url, seller_name, availability, badges, sponsored). Items holds the query's actual matches; when a query matches little or nothing Walmart fills the page with an "other options to consider" block, and those products are returned separately as related_items so they are never mistaken for results. A query that matches nothing comes back with empty items and a populated related_items. Sort by best_match, price_low, price_high, best_seller, rating_high or new. Prices and availability follow the store Walmart assigns to the browser's location. Walmart can refuse many searches sent close together: pace fan-outs, and retry later when it does.

- Site: walmart.com
- Address: `reduck/walmart.com/search-products`
- Updated: 2026-10-22 (v5)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/walmart.com/search-products`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/walmart.com/search-products
```

## Input

- `query` (string, required): Free-text search query.
- `page` (integer, optional): Result page (1-based). Walmart caps pagination around 15-25 pages; max_page in the result says where. Same page re-fetched returns the same organic order; sponsored tiles rotate.
- `sort` (string, optional): Walmart's own sort options.

## Output

- `url` (string, required)
- `page` (integer, required)
- `sort` (string, required)
- `items` (array, required): The query's actual matches, and only those. Walmart pads a page that matches little or nothing with an 'Other options to consider' block; those products are kept out of here and returned in related_items, so the length of this array tracks total_count instead of the tile count on screen. An empty array means the query matched nothing, which is a real answer rather than a failure.
- `query` (string, required)
- `max_page` (integer | null, required): Last page Walmart will serve for this query.
- `total_count` (integer | null, required): Walmart's own count of real matches for the query. It tracks items, not the number of tiles rendered: a page can show dozens of products while this is 0.
- `related_count` (integer, required): How many suggestions are in related_items. A high number next to a low total_count means Walmart mostly padded the page.
- `related_items` (array, required): Products Walmart suggests under 'Other options to consider' when the query matches little or nothing. Same shape as items. These are NOT results for the query and must not be treated as matches: for a query matching nothing they are the entire page. Empty for a query with plenty of matches.
- `corrected_query` (string | null, required): Query Walmart actually searched when it auto-corrected the spelling; null otherwise.

## FAQ

### What does "Search Walmart products" do?

Search Walmart.com by free-text query and return one page of results. Returns query, page, sort, url, total_count, max_page, corrected_query, items and related_items (each item: us_item_id, name, url, price, was_price, unit_price, rating, review_count, image_url, seller_name, availability, badges, sponsored). Items holds the query's actual matches; when a query matches little or nothing Walmart fills the page with an "other options to consider" block, and those products are returned separately as related_items so they are never mistaken for results. A query that matches nothing comes back with empty items and a populated related_items. Sort by best_match, price_low, price_high, best_seller, rating_high or new. Prices and availability follow the store Walmart assigns to the browser's location. Walmart can refuse many searches sent close together: pace fan-outs, and retry later when it does.

### How do I automatically search Walmart products on walmart.com?

Ask an AI agent connected to Reduck to run reduck/walmart.com/search-products, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/search-products

### Is there a walmart.com API to search Walmart products?

You do not need one. "Search Walmart products" drives the real walmart.com pages in a browser, so it works whether or not walmart.com offers an API for this.

### What information do I need to provide?

Required: query. Optional: page, sort.

### What does it return?

It returns url, page, sort, items, query, max_page, total_count, related_count, related_items, corrected_query.

### Do I need to be logged in to walmart.com?

No. It only uses pages of walmart.com that are reachable without signing in.

### Does it change anything on walmart.com, or only read data?

It only reads. It looks things up on walmart.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/walmart.com/search-products, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/search-products

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/walmart.com/search-products
