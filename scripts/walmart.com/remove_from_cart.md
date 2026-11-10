# Remove Walmart product from cart

Automatically remove Walmart product from cart on walmart.com. Remove a product from your Walmart.com cart by item id, whatever its quantity, and return what is left in the cart (lines, item count, subtotal). A product that is not in the cart is reported as not present rather than failing. Walmart sometimes refuses automated cart changes with its "Robot or human?" check; the run then fails saying so, and it usually clears after a pause.

- Site: walmart.com
- Address: `reduck/walmart.com/remove_from_cart`
- Updated: 2026-10-27 (v2)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/walmart.com/remove_from_cart`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/walmart.com/remove_from_cart
```

## Input

- `itemId` (string, required): Walmart item id (us_item_id) of the cart line, as list_cart_items returns it.

## Output

- `lines` (array, required): The cart's lines after the removal.
- `us_item_id` (string, required)
- `was_present` (boolean, required): False when the product was not in the cart; nothing was changed then.
- `subtotal` (string | null, optional): Subtotal after the removal as Walmart displays it; null for an empty cart.
- `cart_count` (integer | null, optional)

## FAQ

### What does "Remove Walmart product from cart" do?

Remove a product from your Walmart.com cart by item id, whatever its quantity, and return what is left in the cart (lines, item count, subtotal). A product that is not in the cart is reported as not present rather than failing. Walmart sometimes refuses automated cart changes with its "Robot or human?" check; the run then fails saying so, and it usually clears after a pause.

### How do I automatically remove Walmart product from cart on walmart.com?

Ask an AI agent connected to Reduck to run reduck/walmart.com/remove_from_cart, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/remove_from_cart

### Is there a walmart.com API to remove Walmart product from cart?

You do not need one. "Remove Walmart product from cart" drives the real walmart.com pages in a browser, so it works whether or not walmart.com offers an API for this.

### What information do I need to provide?

Required: itemId.

### What does it return?

It returns lines, subtotal, cart_count, us_item_id, was_present.

### Do I need to be logged in to walmart.com?

No. It only uses pages of walmart.com that are reachable without signing in.

### Does it change anything on walmart.com, or only read data?

It makes changes on walmart.com, like sending, posting, booking or buying something.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/walmart.com/remove_from_cart, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/remove_from_cart

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/walmart.com/remove_from_cart
