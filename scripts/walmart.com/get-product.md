# Get Walmart product

Automatically get Walmart product on walmart.com. Fetch one Walmart.com item page by its item id (the number in /ip/.../<id>). Returns us_item_id, product_id, url, name, brand, model, upc, price, was_price, currency, availability, seller, rating, review_count, rating_breakdown, category path, images, short/long description (HTML), specifications, variants (with each option's item id), return_policy and badges. The requested id can resolve to a different displayed variant; both ids are returned. Price and availability follow the store Walmart assigns to the browser's location.

- Site: walmart.com
- Address: `reduck/walmart.com/get-product`
- Updated: 2026-10-22 (v2)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/walmart.com/get-product`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/walmart.com/get-product
```

## Input

- `itemId` (string, required): Walmart item id (us_item_id), the trailing number of an /ip/ URL; also returned by search-products.

## Output

- `url` (string, required): Canonical item URL.
- `name` (string, required)
- `us_item_id` (string, required): Item id actually displayed (differs when Walmart resolves to another variant).
- `requested_item_id` (string, required): Item id passed by the caller; the join key.
- `upc` (string | null, optional)
- `brand` (string | null, optional)
- `model` (string | null, optional)
- `price` (number | null, optional): Current price. Null when the page shows no single price.
- `badges` (array, optional)
- `images` (array, optional)
- `rating` (number | null, optional)
- `seller` (object, optional)
- `category` (array, optional): Breadcrumb path; empty when the page has none.
- `currency` (string | null, optional)
- `variants` (array, optional): Variant axes (e.g. Actual Color); empty when the product has no variations.
- `was_price` (number | null, optional): Struck-through previous price, when shown.
- `product_id` (string | null, optional): Walmart's internal product id for the displayed variant.
- `availability` (string | null, optional): Walmart's availability code for the assigned store, e.g. IN_STOCK, OUT_OF_STOCK.
- `review_count` (integer | null, optional)
- `return_policy` (string | null, optional)
- `specifications` (array, optional): Spec table; empty when the page has none.
- `long_description` (string | null, optional): HTML as served.
- `rating_breakdown` (object | null, optional): Number of ratings per star bucket, e.g. {"5_star": 4348}.
- `short_description` (string | null, optional): HTML as served.

## FAQ

### What does "Get Walmart product" do?

Fetch one Walmart.com item page by its item id (the number in /ip/.../<id>). Returns us_item_id, product_id, url, name, brand, model, upc, price, was_price, currency, availability, seller, rating, review_count, rating_breakdown, category path, images, short/long description (HTML), specifications, variants (with each option's item id), return_policy and badges. The requested id can resolve to a different displayed variant; both ids are returned. Price and availability follow the store Walmart assigns to the browser's location.

### How do I automatically get Walmart product on walmart.com?

Ask an AI agent connected to Reduck to run reduck/walmart.com/get-product, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/get-product

### Is there a walmart.com API to get Walmart product?

You do not need one. "Get Walmart product" drives the real walmart.com pages in a browser, so it works whether or not walmart.com offers an API for this.

### What information do I need to provide?

Required: itemId.

### What does it return?

It returns upc, url, name, brand, model, price, badges, images, rating, seller, category, currency, variants, was_price, product_id, us_item_id, availability, review_count, return_policy, specifications, long_description, rating_breakdown, requested_item_id, short_description.

### Do I need to be logged in to walmart.com?

No. It only uses pages of walmart.com that are reachable without signing in.

### Does it change anything on walmart.com, or only read data?

It only reads. It looks things up on walmart.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/walmart.com/get-product, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/get-product

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/walmart.com/get-product
