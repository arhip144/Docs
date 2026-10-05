---
description: Gifts (manager-gifts) on the site
icon: gift
---

# Gifts (website)

Path: `/dashboard/:guildId/gifts` → `/gifts/:giftId`

{% hint style="warning" %}
Creating and editing gifts requires [premium](../premium.md).
{% endhint %}

## Fields

| Field | Description |
| --- | --- |
| Gift name | Required |
| Emoji | Emoji |
| Enabled | Available to claim |
| Color | Embed color |
| Items | Rewards: XP / RP / currency / items |
| Max. unique users | How many different people can claim |
| Gift claim count | Claim limit |
| Cooldown (seconds) | Pause between claims |
| Start / end date | Availability window |
| Comment | Text |
| Image / Thumbnail | URL |
| Permission | [Permission](permissions.md) object |
| Recipients | User list (if restricted) |
| Button ID | For a button in [message builder](message-builder.md) / Discord components |

Discord: [Creation of gifts (manager-gifts)](../guide/gifts.md).
