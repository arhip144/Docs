---
description: Creating and editing achievements on the site
icon: trophy
---

# Achievements (website)

Path: `/dashboard/:guildId/achievements` → `/achievements/:achievementId`

{% hint style="info" %}
Limit: **5** without premium, **1000** with premium.
{% endhint %}

## Basic fields

| Field | Description |
| --- | --- |
| Name | 2–30 characters |
| Emoji | Achievement emoji |
| Enabled | Whether the achievement is active |

## Task

| Field | Description |
| --- | --- |
| Select task | Condition type (list below) or “Custom task” |
| Amount | Threshold XX (if numeric type) |
| Task items | Up to 5 items (for “find/craft/catch/mine item” types) |
| Task roles | Up to 10 roles (“Obtain role” type) |

### Task types

- Send XX messages in chat
- Spend XX hours in voice chat
- Receive XX likes
- Invite XX people to the server
- Bump the server XX time(s)
- Earn / spend currency (XX)
- Fish / mine XX time(s)
- Find / craft item
- Touch a wormhole XX time(s)
- Claim daily reward XX day(s) in a row
- Reach reputation XX
- Complete quests XX time(s)
- Find all items
- Create giveaway / win giveaway XX time(s)
- Sell XX items on the market
- Spend XX h in a row in voice
- Open / obtain / craft / use / buy / sell XX items
- Spawn wormhole XX time(s)
- Obtain role
- Reach level XX / seasonal level XX
- Vote for bot / donate (support server)
- Complete all achievements
- Boost server XX time(s)
- Work XX time(s)
- Catch / mine item
- Use promocode XX time(s)
- Be on server XX minutes
- Win a bet of XX or more in Crash

## Rewards

Up to 5 rewards. Types: XP / Reputation / Currency / Item / Role + quantity.

Discord: [Creation of achievements](../guide/achievements.md).
