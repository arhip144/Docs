---
icon: masks-theater
description: Role inventory — storing and equipping Discord roles
---

# Role inventory

## What is this?

Roles can be stored in the inventory and put on or taken off without losing them permanently. Handy for custom and temporary roles.

## Viewing

Command [/inventory-roles](../commands/inventory.md)

## Ways to get a role into the inventory

1. Remove a role from your profile
2. Open it from an [item](items/)
3. Buy it on the [market](market.md) (`/market`, premium)
4. Win it in a giveaway (`/manager-giveaways`, premium)
5. Reward for a [quest](quests.md)
6. Transfer (`/transfer-role`)
7. [Custom role](custom-role.md)
8. The admin command `/give role`
9. Reward for an [achievement](achievements.md)

## Conditions for removing a role from the profile

Command [/role-properties](../commands/admins.md) → the **Can be removed** property = Yes.

<figure><img src="../.gitbook/assets/Скриншот 21-01-2024 163445.png" alt=""><figcaption></figcaption></figure>

Other flags: cannot be transferred / sold / given away / auctioned. On the website, use the [Administration → Role properties](../website/moderation.md) tab.

{% hint style="warning" %}
Removing and equipping require the "Manage Roles" permission; the role must be below the bot's role.
{% endhint %}
