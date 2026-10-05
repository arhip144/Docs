---
description: Promocodes on the site
icon: ticket
---

# Promocodes (website)

Path: `/dashboard/:guildId/promocodes` → `/promocodes/:code`

{% hint style="info" %}
Limit: **5** without premium, **1000** with premium. Without premium, extra promocodes may be frozen.
{% endhint %}

## Fields

| Field | Description |
| --- | --- |
| Promocode | Code (string) |
| Enabled | Active (rewards must include items) |
| Use count | Activation limit |
| Promocode items | Rewards |
| Use reset cron pattern | [Cron](../guide/cron-patterns.md) |
| Disable date | When to turn off |
| Delete date | When to delete |
| Promocode permission | [Permission](permissions.md) object |
| Uses | List of users who activated the code |

See also [Autogenerators](autogenerators.md).

Discord: [Promocodes](../guide/promocodes.md).
