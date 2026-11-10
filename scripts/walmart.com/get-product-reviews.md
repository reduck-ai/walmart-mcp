# Get Walmart product reviews

Automatically get Walmart product reviews on walmart.com. Fetch one page of customer reviews (10 per page) for a Walmart.com item id, anonymously. Sort by relevancy, helpful, submission-desc, submission-asc, rating-desc or rating-asc; optionally restrict to verified purchases. Returns product (us_item_id, name), summary (average_rating, total_ratings, reviews_with_text, recommended_percentage, rating_breakdown), the page, sort, filtered_count and reviews (id, rating, title, text, date, author, verified_purchase, recommended, helpful_votes, unhelpful_votes, variant). Only reviews with text are listed; ratings without text count in the summary only.

- Site: walmart.com
- Address: `reduck/walmart.com/get-product-reviews`
- Updated: 2026-10-22 (v4)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/walmart.com/get-product-reviews`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/walmart.com/get-product-reviews
```

## Input

- `itemId` (string, required): Walmart item id (us_item_id), the trailing number of an /ip/ URL; also returned by search-products.
- `page` (integer, optional): Review page, 10 reviews each. One page per call; the caller loops. Beyond the last page Walmart returns an empty list. With a submission-* sort the set shifts as new reviews arrive; relevancy and helpful are stable under replay.
- `sort` (string, optional): Walmart's own sort options. submission-desc = newest first.
- `verifiedOnly` (boolean, optional): Restrict to verified purchases (Walmart's "Verified purchases only" toggle).

## Output

- `page` (integer, required)
- `sort` (string, required)
- `product` (object, required)
- `reviews` (array, required)
- `summary` (object, required)
- `verified_only` (boolean, required)
- `filtered_count` (integer | null, required): Number of written reviews matching the active filter; divide by 10 for the page count.

## FAQ

### What does "Get Walmart product reviews" do?

Fetch one page of customer reviews (10 per page) for a Walmart.com item id, anonymously. Sort by relevancy, helpful, submission-desc, submission-asc, rating-desc or rating-asc; optionally restrict to verified purchases. Returns product (us_item_id, name), summary (average_rating, total_ratings, reviews_with_text, recommended_percentage, rating_breakdown), the page, sort, filtered_count and reviews (id, rating, title, text, date, author, verified_purchase, recommended, helpful_votes, unhelpful_votes, variant). Only reviews with text are listed; ratings without text count in the summary only.

### How do I automatically get Walmart product reviews on walmart.com?

Ask an AI agent connected to Reduck to run reduck/walmart.com/get-product-reviews, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/get-product-reviews

### Is there a walmart.com API to get Walmart product reviews?

You do not need one. "Get Walmart product reviews" drives the real walmart.com pages in a browser, so it works whether or not walmart.com offers an API for this.

### What information do I need to provide?

Required: itemId. Optional: page, sort, verifiedOnly.

### What does it return?

It returns page, sort, product, reviews, summary, verified_only, filtered_count.

### Do I need to be logged in to walmart.com?

No. It only uses pages of walmart.com that are reachable without signing in.

### Does it change anything on walmart.com, or only read data?

It only reads. It looks things up on walmart.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/walmart.com/get-product-reviews, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/get-product-reviews

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/walmart.com/get-product-reviews
