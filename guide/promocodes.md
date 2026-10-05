---
description: Creating and managing promocodes
icon: ticket
---

# Promocodes

## What is this?

Promocodes give rewards (items, currency, XP, RP) for a code. You can limit the number of activations, permissions, and dates.

{% hint style="info" %}
Limit: **5** without premium, **1000** with premium. Extra promocodes may be frozen without premium.
{% endhint %}

## Discord

Command: [/manager-promocodes](../commands/admins.md) (`create` / `edit` / `delete` / `view`).

Typical settings:

| Parameter | Description |
| --- | --- |
| Code | The promocode string |
| Enabled | Rewards are required |
| Number of uses | Activation limit |
| Items | Rewards |
| Reset cron | Resetting the counter; [cron](cron-patterns.md) |
| Disable / delete dates | When to disable or delete |
| Permission | A [permission](permissions.md) preset |

Automatic code publishing: [Autogenerators](autogenerators.md).

## On the website

{% content-ref url="../website/promocodes.md" %}
[promocodes.md](../website/promocodes.md)
{% endcontent-ref %}
