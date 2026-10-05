---
description: Full guide to creating and editing items on the site
icon: box
---

# Items (website)

Path: `/dashboard/:guildId/items` → edit `/dashboard/:guildId/items/:itemId`

On the list page you can create, open, and delete items. The editor saves changes with the button at the bottom of the page.

{% hint style="info" %}
Slot limit: **25** without premium, **1000** with premium. See [Premium](../premium.md).
{% endhint %}

{% hint style="info" %}
The same in Discord via `/manager-items`. Short Discord guide: [Items](../guide/items/).
{% endhint %}

## Basic fields

Always visible at the top of the editor.

| Field | Description |
| --- | --- |
| Emoji | Item emoji. Server custom emojis — with premium |
| Item name | 2–30 characters. Reserved names forbidden (`currency`, `rp`, `copy`, etc.) |
| Rarity name | Up to 45 characters |
| Sort order | 1–1000, affects order in lists |
| Item color | Border/display color |
| Item description | Up to 200 characters |
| Item image | Image URL |

## Tabs

### Shop

| Field | Description |
| --- | --- |
| In shop / Not in shop | Whether the item appears in `/shop` |
| Quantity | Stock left; can be ∞ |
| Buy price | Item/currency; static or dynamic (crypto pair + multiplier) |
| Sell price | Same as buy price |
| Reputation discount/penalty on buy | Buy price modifier |
| Reputation bonus/penalty on sell | Sell price modifier |
| Daily / weekly / monthly buy limit | How many times can be bought per period |
| Daily / weekly / monthly delivery | Type: increases or sets stock quantity + value |

More on crypto prices: [Cryptocurrency](../guide/items/cryptocurrency.md).

### Craft

Up to 10 recipes. In each recipe:

| Field | Description |
| --- | --- |
| Ingredients | Up to 10 “item + quantity” pairs |
| Min. / Max. result | How many items are produced |
| Recipe known | Whether players see the recipe |
| Craft permission | [Permission](permissions.md) object |
| Cooldown (sec) | Pause between crafts |
| Min. / Max. per action | Quantity range per action |

Players craft with `/craft`.

### Case

| Field | Description |
| --- | --- |
| Mode | One item / Multiple items |
| Contents | Up to 10 slots. Type: Item / Currency / XP / Reputation / Role / Steam game / Cookies (on specific servers) |
| Min. / Max. | Quantity range |
| Chance % | Drop weight |
| Role duration (min) | For “Role” type |
| Search currency | For Steam game (RUB, UAH, KZT, TL, USD) |
| Key to open | Item / currency / XP / RP + quantity |

Players open cases via `/open` or inventory on [profile](profile.md).

### Use

The item becomes usable (`/use`) if at least one action is set.

#### Rewards

| Action | Parameters |
| --- | --- |
| Grant level / reputation / XP / currency | Value |
| Grant item | Item + quantity |
| Grant role | Role; optional “directly in Discord”; duration in minutes |
| Grant trophy | Trophy text |

#### Boosters

| Action | Parameters |
| --- | --- |
| Currency / XP / luck / reputation booster | Multiplier %, minutes |
| Clear currency / XP / luck / reputation booster | Toggle |

#### Message

| Action | Parameters |
| --- | --- |
| Message | Text (up to 1000) |
| DM message | Toggle (text required) |
| Thumbnail / Image | URL |
| Border color | HEX |

#### Progress

| Action | Parameters |
| --- | --- |
| Achievement | Select achievement |
| Spawn wormhole | Select wormhole |
| Study item / recipe | Item |
| Grant quest | Quest |
| Role auto-income (min) | Minutes |

#### Removal

| Action | Parameters |
| --- | --- |
| Clear role / trophy | Role or text |
| Remove item from server | Item |
| Reset / remove quest | Quest |
| Subtract XP / currency / reputation / level | Value |
| Subtract item | Item + quantity |

### Obtaining methods

| Source | Fields |
| --- | --- |
| Fishing / Mining | Chance %, min/max qty, min/max XP |
| Voice / text channel | Chance and quantities |
| Like / invite / server bump | Chance and quantities (bump — premium) |
| Daily reward (days 1–7) | Min/max per day |

### Properties

| Field | Description |
| --- | --- |
| Known | If off — info hidden until the item is obtained or studied |
| Visible | If off — cannot obtain or interact |
| Transferable | Allows `/transfer` |
| Droppable | Allows `/drop` |
| Giveable | Giveaways (server premium required) |
| Sellable on market | Market (premium) |
| Sellable on auction | Auctions |
| Crash bettable | Crash bets |
| Blackjack bettable | Blackjack bets |

### Permissions (premium)

Link [permission](permissions.md) objects to actions:

Permission to buy, sell, open, use, transfer, drop; obtain via message / voice / like / invite / bump / fishing / mining.

### Cooldowns

For **Use**, **Open**, **Sell**, **Drop**, **Transfer**:

| Field | Description |
| --- | --- |
| Cooldown (sec) | Up to 2,592,000 (30 days) |
| Min. per action | Minimum quantity per action |
| Max. per action | Maximum quantity per action |

## Related sections

{% content-ref url="categories.md" %}
[categories.md](categories.md)
{% endcontent-ref %}

{% content-ref url="../guide/items/" %}
[items](../guide/items/)
{% endcontent-ref %}
