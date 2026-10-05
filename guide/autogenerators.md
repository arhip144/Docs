---
description: Automatic generation and publishing of promocodes
icon: wand-magic-sparkles
---

# Promocode autogenerators

## What is this?

On a [cron schedule](cron-patterns.md), the bot creates a promocode from a reward pool and publishes it to a channel.

{% hint style="warning" %}
Available with [premium](../premium.md) only (up to 25 autogenerators). Command: [/promocode-autogenerators](../commands/admins.md).
{% endhint %}

## What can be configured

| Parameter | Description |
| --- | --- |
| Name / enabled | Basic flags |
| Publishing channel | Where to send the code |
| Cron pattern | When to generate |
| Generations left | A limit or unlimited |
| Lifetime / uses | Parameters of the created promocode |
| Reward pool | Rewards with chances (sum ≤ 100%) |
| Permission | Who can activate it |

Related to [promocodes](promocodes.md).

## On the website

{% content-ref url="../website/autogenerators.md" %}
[autogenerators.md](../website/autogenerators.md)
{% endcontent-ref %}
