# List Walmart cart items

Automatically list Walmart cart items on walmart.com. List the items in your Walmart.com cart: for each line its item id, name, quantity, unit price, line total, seller and availability, plus the cart's item count and subtotal, and whether the cart belongs to a signed-in account or to this browser's guest cart. An empty cart returns an empty list. Saved-for-later items are not included. Walmart sometimes refuses automated visits with its "Robot or human?" check; the run then fails saying so, and it usually clears after a pause.

- Site: walmart.com
- Address: `reduck/walmart.com/list_cart_items`
- Updated: 2026-10-27 (v2)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/walmart.com/list_cart_items`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/walmart.com/list_cart_items
```

## Input

It takes no input.

## Output

- `lines` (array, required)
- `subtotal` (string | null, optional): Cart subtotal as Walmart displays it, e.g. $7.94; null for an empty cart.
- `signed_in` (boolean | null, optional): True for a signed-in account's cart, false for this browser's guest cart.
- `cart_count` (integer | null, optional): Total quantity across the cart's lines.

## FAQ

### What does "List Walmart cart items" do?

List the items in your Walmart.com cart: for each line its item id, name, quantity, unit price, line total, seller and availability, plus the cart's item count and subtotal, and whether the cart belongs to a signed-in account or to this browser's guest cart. An empty cart returns an empty list. Saved-for-later items are not included. Walmart sometimes refuses automated visits with its "Robot or human?" check; the run then fails saying so, and it usually clears after a pause.

### How do I automatically list Walmart cart items on walmart.com?

Ask an AI agent connected to Reduck to run reduck/walmart.com/list_cart_items, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/list_cart_items

### Is there a walmart.com API to list Walmart cart items?

You do not need one. "List Walmart cart items" drives the real walmart.com pages in a browser, so it works whether or not walmart.com offers an API for this.

### What information do I need to provide?

Nothing. It takes no input.

### What does it return?

It returns lines, subtotal, signed_in, cart_count.

### Do I need to be logged in to walmart.com?

No. It only uses pages of walmart.com that are reachable without signing in.

### Does it change anything on walmart.com, or only read data?

It only reads. It looks things up on walmart.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/walmart.com/list_cart_items, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/list_cart_items

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/walmart.com/list_cart_items
