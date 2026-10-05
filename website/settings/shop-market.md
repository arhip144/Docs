---
description: “Shop”, “Market”, and “Auctions” tabs
icon: cart-shopping
---

# Shop, market, auctions

## Shop

Server bot shop (`/shop`, `/buy`). Assortment is set on [items](../items.md) and [categories](../categories.md).

| Field | Description |
| --- | --- |
| Shop name | Up to 25 characters |
| Shop thumbnail | Thumbnail URL |
| Shop messages | Up to 10 lines (up to 50 characters). Placeholders: `{member}`, `{currency}`, `{guild}` |

## Market

Player-to-player listings on the site and in Discord. Requires server [premium](../../premium.md).

| Field | Description |
| --- | --- |
| Market channel | Where listings are posted |
| Listing lifetime (days) | 0–365 |

See [Market on the site](../market.md).

## Auctions

| Field | Description |
| --- | --- |
| Auction channel | Announcement channel |
| Auction permission | [Permission](../permissions.md) object |
