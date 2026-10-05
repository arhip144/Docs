---
description: Wormholes on the site
icon: hurricane
---

# Wormholes (website)

Path: `/dashboard/:guildId/wormholes` → `/wormholes/:wormholeId`

{% hint style="info" %}
Limit: **5** without premium, **100** with premium.
{% endhint %}

## Fields

| Field | Description |
| --- | --- |
| Name | Wormhole name |
| Enabled | Requires item, chance, quantity, cron, and channel |
| Permission | Who can claim |
| Item | Reward: item / currency / XP / RP |
| Chance | Spawn chance up to 100% |
| Quantity from / to | Reward range |
| Cron pattern | When to spawn; [reference](../guide/cron-patterns.md) |
| Spawns left | Unlimited or limit |
| Webhook channel | Publish channel |
| Style | [Wormhole style](styles.md) |
| Lifetime | Seconds until despawn |
| Delete after claim | Remove message after claim |
| Show date | Display spawn date |

Discord: [Wormholes](../guide/wormholes.md).
