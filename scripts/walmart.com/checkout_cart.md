# Check out Walmart cart

Automatically check out Walmart cart on walmart.com. Check out your Walmart.com cart up to the review page, without ordering. It uses the account's preselected shipping address, or the store when the cart is set to pickup, and the saved payment method, confirming the address when Walmart asks for it. It returns the items, whether the order is delivered or picked up, the address or the pickup store, the payment method, and the order summary (subtotal, shipping, taxes, estimated total). Fails on an empty cart, when the browser is not signed in to Walmart, when the account has no saved address or card, and when Walmart reports items unavailable for the address (it names them; remove them with Remove Walmart product from cart). When Walmart keeps refusing the visit, the run fails saying so; retry later.

- Site: walmart.com
- Address: `reduck/walmart.com/checkout_cart`
- Updated: 2026-11-20 (v4)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/walmart.com/checkout_cart`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/walmart.com/checkout_cart
```

## Input

It takes no input.

## Output

- `url` (string, required): The review page URL.
- `stage` (string, required)
- `lines` (array, optional)
- `taxes` (string | null, optional): As Walmart shows it; can be Pending until the address is confirmed.
- `address` (string | null, optional): Shipping address the checkout uses. Null for pickup.
- `payment` (string | null, optional): Payment method the checkout uses, as Walmart names it (card type and last four digits).
- `shipping` (string | null, optional): Shipping or below-minimum fee, when Walmart charges one.
- `subtotal` (string | null, optional)
- `contract_id` (string | null, optional): Walmart's id for this checkout.
- `fulfillment` (string, optional): delivery when the order ships to the address, pickup when the cart is set to pickup at a store.
- `order_total` (string | null, optional): Walmart's estimated total.
- `pickup_store` (string | null, optional): For pickup: the store's name and address. Null for delivery.

## FAQ

### What does "Check out Walmart cart" do?

Check out your Walmart.com cart up to the review page, without ordering. It uses the account's preselected shipping address, or the store when the cart is set to pickup, and the saved payment method, confirming the address when Walmart asks for it. It returns the items, whether the order is delivered or picked up, the address or the pickup store, the payment method, and the order summary (subtotal, shipping, taxes, estimated total). Fails on an empty cart, when the browser is not signed in to Walmart, when the account has no saved address or card, and when Walmart reports items unavailable for the address (it names them; remove them with Remove Walmart product from cart). When Walmart keeps refusing the visit, the run fails saying so; retry later.

### How do I automatically check out Walmart cart on walmart.com?

Ask an AI agent connected to Reduck to run reduck/walmart.com/checkout_cart, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/checkout_cart

### Is there a walmart.com API to check out Walmart cart?

You do not need one. "Check out Walmart cart" drives the real walmart.com pages in a browser, so it works whether or not walmart.com offers an API for this.

### What information do I need to provide?

Nothing. It takes no input.

### What does it return?

It returns url, lines, stage, taxes, address, payment, shipping, subtotal, contract_id, fulfillment, order_total, pickup_store.

### Do I need to be logged in to walmart.com?

Yes. It acts as you on walmart.com: on your own Chrome it reuses your session, and on a Reduck-hosted browser it loads the walmart.com cookies saved by the Reduck extension.

### Does it change anything on walmart.com, or only read data?

It makes changes on walmart.com, like sending, posting, booking or buying something.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/walmart.com/checkout_cart, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/walmart.com/checkout_cart

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/walmart.com/checkout_cart
