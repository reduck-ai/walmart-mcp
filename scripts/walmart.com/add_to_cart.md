# Add Walmart product to cart

Automatically add Walmart product to cart on walmart.com. Add a product to your Walmart.com cart by item id, with an optional quantity. A product already in the cart has the quantity added to the one it has. Returns the product's cart line after the add (quantity, unit price, line total, seller), the cart's item count and subtotal, and whether the cart belongs to a signed-in account or to this browser's guest cart. Items with no add-to-cart button (out of stock, sold only in store) fail with Walmart's availability for them. Walmart sometimes refuses automated cart changes with its "Robot or human?" check; the run then fails saying so, and it usually clears after a pause.

- Site: walmart.com
- Address: `reduck/walmart.com/add_to_cart`
- Updated: 2026-10-27 (v2)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/walmart.com/add_to_cart`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/walmart.com/add_to_cart
```

## Input

- `itemId` (string, required): Walmart item id (us_item_id), the trailing number of an /ip/ URL; also returned by search-products.
- `quantity` (integer, optional): How many to add.

## Output

- `line` (object | null, required): The product's cart line after the add; null if Walmart did not keep it in the cart.
- `us_item_id` (string, required): Item id actually added (differs when Walmart resolves the page to another variant).
- `requested_item_id` (string, required): Item id passed by the caller.
- `subtotal` (string | null, optional): Cart subtotal as Walmart displays it, e.g. $7.94.
- `signed_in` (boolean | null, optional): True for a signed-in account's cart, false for this browser's guest cart.
- `cart_count` (integer | null, optional): Total quantity across the cart's lines.

## FAQ

### What does "Add Walmart product to cart" do?

Add a product to your Walmart.com cart by item id, with an optional quantity. A product already in the cart has the quantity added to the one it has. Returns the product's cart line after the add (quantity, unit price, line total, seller), the cart's item count and subtotal, and whether the cart belongs to a signed-in account or to this browser's guest cart. Items with no add-to-cart button (out of stock, sold only in store) fail with Walmart's availability for them. Walmart sometimes refuses automated cart changes with its "Robot or human?" check; the run then fails saying so, and it usually clears after a pause.

### How do I automatically add Walmart product to cart on walmart.com?

Ask an AI agent connected to Reduck to run reduck/walmart.com/add_to_cart, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/add_to_cart

### Is there a walmart.com API to add Walmart product to cart?

You do not need one. "Add Walmart product to cart" drives the real walmart.com pages in a browser, so it works whether or not walmart.com offers an API for this.

### What information do I need to provide?

Required: itemId. Optional: quantity.

### What does it return?

It returns line, subtotal, signed_in, cart_count, us_item_id, requested_item_id.

### Do I need to be logged in to walmart.com?

No. It only uses pages of walmart.com that are reachable without signing in.

### Does it change anything on walmart.com, or only read data?

It makes changes on walmart.com, like sending, posting, booking or buying something.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/walmart.com/add_to_cart, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/add_to_cart

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/walmart.com/add_to_cart
