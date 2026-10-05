---
description: Promocode autogenerators on the site
icon: wand-magic-sparkles
---

# Promocode autogenerators (website)

Path: `/dashboard/:guildId/autogenerators` → `/autogenerators/:autogeneratorId`

{% hint style="warning" %}
Available only with [premium](../premium.md) (up to 25 autogenerators).
{% endhint %}

## Fields

| Field | Description |
| --- | --- |
| Name | Autogenerator name |
| Enabled | Requires channel, cron, and at least one reward |
| Permission | [Permission](permissions.md) object |
| Publish channel | Where to post the promocode |
| Cron pattern | When to create; [reference](../guide/cron-patterns.md) |
| Generations left | Unlimited or limit |
| Generation cycles | Number of cycles |
| Lifetime | Promocode lifetime in minutes |
| Uses | Activation limit for created code |
| Generate promocode | Manual run (after save) |
| Reward pool | Reward list with chances (sum ≤ 100%) |

Discord: [Autogenerators](../guide/autogenerators.md).
