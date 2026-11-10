# Walmart MCP

Walmart has no consumer API: its developer APIs are for sellers, suppliers and advertisers. This Walmart MCP server (Model Context Protocol) lets Claude, ChatGPT or any AI agent search Walmart products and add your grocery list to your Walmart cart, in your own Chrome, with no API key.

- Product: Reduck MCP
- Updated: 2026-10-27

![One integration, every website](https://docs.reduck.ai/overview/one-integration-every-website.png)

[Reduck MCP](https://docs.reduck.ai) gives your agent reusable browser scripts for the sites that have no API. They run in your own Chrome, through the Reduck extension, where you are already signed in: no credentials exposed, and no bot detection.

**Get started:** [docs.reduck.ai](https://docs.reduck.ai)

## Overview

You have a grocery list, from a meal plan, a recipe or a note on your phone. Your AI agent can read it. The part it usually cannot do is the last one: find each item on Walmart and put it in your Walmart cart, so that you only check the cart and order.

## Why it's hard

There is no Walmart shopping API for consumers. Walmart's developer APIs serve sellers, suppliers and advertisers, and the cart API on walmart.io is for partners. Walmart's own Agent Gateway uses MCP, but it starts as a beta for companies and developers. A browser agent that clicks through walmart.com by itself spends hours on "search for milk, add to cart", and Walmart is quick to show its "Robot or human?" check to a new, empty browser.

## How Reduck does it

Reduck is an MCP server whose Walmart scripts run in your own Chrome, where you are already signed in. Your agent gets one tool per step: search Walmart products, read a product, read its reviews, add an item to your Walmart cart, list the cart, remove a line. It works through your list one item at a time, with the prices and availability of the store Walmart assigns to your browser, and fills your real cart. It can open the checkout up to the review page and read you the address, payment method and total. You place the order.

## What your agent does

- Search Walmart for each item of your grocery list, with price, unit price, rating and availability
- Open a product for its sizes, variants and specifications, or read its reviews
- Add each item to your Walmart cart, with the quantity you need
- Tell you which items are out of stock or sold only in store
- List the cart and its subtotal, and remove what you do not want
- Open the checkout up to the review page and read the items, address, payment method and total

## Agent Gateway, Zinc, your own script or Reduck

| | Walmart Agent Gateway | Zinc Walmart Shopping API | Your own Playwright script | **Reduck** |
|---|---|---|---|---|
| Who can use it | A beta for companies and developers | Developers with a Zinc account | Anyone who writes and maintains code | **Any MCP client: Claude, ChatGPT, Cursor, local agents** |
| Setup | An agent profile linked to your Walmart account | Zinc's managed Walmart accounts, or your Walmart credentials | A browser you log in to and keep running | **Stay signed in to Walmart in Chrome** |
| Search and add to cart | Not documented in detail | Product data; cart step not documented | You write each step | **One script per step** |
| Order | With your approval or a spending limit | Placed from a product URL, with a maximum price | You write it | **You place it, after the agent's review** |
| Acts as | An agent profile on your account | Zinc's account, or yours | A logged-in automation | **You** |

## Who it's for

- Anyone who plans meals and wants the Walmart cart filled from the list
- Developers who give Claude Code, Cursor or a local agent a Walmart grocery tool
- Hobby projects that hit the "Walmart API is B2B" wall

## FAQ

### Is there an official Walmart MCP server?

Walmart announced the Walmart Agent Gateway on October 21, 2026. It uses MCP and starts as a beta for companies and developers, and Agent Profiles, which link an agent to your Walmart account, launch in the month after. It is not a server that any personal agent can connect to on its own today. Walmart also runs a Developer Docs MCP server (October 14, 2026) for coding assistants: it gives access to Walmart's developer documentation, not to shopping. Reduck is an MCP server too, and its Walmart scripts run in your own Chrome, with any MCP client.

### Does Walmart have an API to add items to my cart?

Not for shoppers. The APIs on developer.walmart.com are for sellers, suppliers, carriers and advertisers. The Pickup and Delivery API on walmart.io describes a shoppable cart, but it needs a partnership with Walmart. For a personal project or a hobby agent, there is no consumer API to call.

### What about Zinc's Walmart Shopping API?

Zinc sells an API that buys on Walmart for you. You send a product URL, a quantity, a shipping address and a maximum price, and Zinc places the order with its own managed Walmart accounts or with the Walmart credentials you give it. Its page does not describe a cart step or pickup, and does not show prices. With Reduck, your agent fills your own Walmart cart in your own Chrome, you give no credentials to a third party, and you place the order.

### How does the agent pick the right product for "milk" or "bread"?

It searches Walmart for each line of your list and reads the results with their price, unit price, rating, seller and availability. It can open a product for its sizes and variants, or read its reviews, before it adds one. Tell it your brands and sizes, and it uses them.

### Does it place the order?

No. The agent fills your cart and can open the checkout up to the review page, with the shipping address and the payment method saved as default on your Walmart account. It reads you the items, the address, the payment method and the total, and names the items Walmart reports as unavailable for that address. You place the order yourself on walmart.com. The checkout needs a signed-in account with a saved address and card.

### Do I need a Walmart API key or my password?

No. There is no API key, no partner account and no password to give. You stay signed in to Walmart in your own Chrome, and the Reduck extension runs each script there. The agent never sees your card number.

### Does it work with Claude Code, Cursor and ChatGPT?

Yes. Reduck connects to Claude, Claude Code, ChatGPT, Codex, Cursor and any other MCP client, local agents included. You give it your list in plain words, and the agent picks the Walmart scripts it needs.

### What about Walmart's rules on AI agents?

Walmart's terms for AI agents say that customers approve agent purchases by default, that agents do not receive payment card information, and that agents do not act beyond what the shopper intends. Each Reduck script runs only when you or your agent asks for it, in your own browser, signed in as you, and the agent stops before the order. Walmart's Terms of Use apply to you as they do when you shop yourself; decide whether that fits how you use your account.

### What if Walmart asks "Robot or human?"

Walmart sometimes shows this check. The script stops and says so, and the check usually clears after a pause. Keep the pace of a person: one list at a time, not hundreds of searches in a row.

Source: https://reduck.ai/use-cases/walmart-mcp
