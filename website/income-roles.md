---
description: Income roles on the site
icon: money-bill
---

# Income roles (website)

Path: `/dashboard/:guildId/roles` → `/roles/:roleId`

{% hint style="info" %}
Limit: **5** without premium, **100** with premium. Players collect income with `/role-income`.
{% endhint %}

## Fields

| Field | Description |
| --- | --- |
| Enabled | Role is active (income must be configured) |
| Role type | Fixed amount / Percent (per hour) |
| Permission | [Permission](permissions.md) object |
| XP | XP income |
| Currency | CUR income |
| Reputation | RP income |
| Cooldown (hours) | Hours until next claim |
| Notification | Notify when income is available |
| Items | Up to 10 items in income |

Discord: [Creating income roles](../guide/roles.md).
