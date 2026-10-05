---
description: Permission presets for items, quests, and other features
icon: key
---

# Permissions

## What is this?

A permission preset is a set of conditions (roles, items, level, UTC time, etc.). It is attached to purchasing an item, a quest, a gift, a promocode, and other actions.

{% hint style="warning" %}
Creating presets requires [premium](../premium.md). Command: [/manager-permissions](../commands/admins.md).
{% endhint %}

## Discord

1. `/manager-permissions create` \<name\>
2. Add requirements (up to 10)
3. Enable the preset
4. Specify its ID in the relevant manager (item, quest, gift…)

Examples of conditions: roles (all / any / except), an item in the inventory, an achievement, a quest, channels, days of the week, level, statistics over a period, booster %.

## On the website

Full list of requirement types:

{% content-ref url="../website/permissions.md" %}
[permissions.md](../website/permissions.md)
{% endcontent-ref %}
