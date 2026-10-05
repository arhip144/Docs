---
description: Server administration on the site — member, server, activities, cooldowns
icon: user-shield
---

# Administration (website)

Path: `/dashboard/:guildId/moderation`

Requires access to the **Administration** section.

## “Member” tab

Select a user, then an action.

### Grant or remove

Adds or subtracts: level, seasonal level, XP, currency, likes, reputation, role (in role inventory).

### Set exact value

Writes an exact value (does not add): level, XP, currency, likes, reputation; luck / XP / currency / reputation boosts.

### Grant or remove item

Adds item to inventory or removes it.

### Achievements / Quests

Grant or remove achievement / quest.

### Trophies

Add a trophy line (max. 10 per user).

### Purchase limits

Reset daily / weekly / monthly limit. Without an item — all limits for the period.

### Activity rewards

Toggles for the selected user (off = reward blocked):

XP / currency / reputation / items × message / voice / invite / bump / like.

## “Server” tab

### Cleanup

Erases selected data. Empty user list = everyone on the server.

Options: currency; level and XP; seasonal level; reputation; inventory; role inventory; achievements; quests; trophies; boosts; shop stock; statistics (alltime/day/week/month/year); job cooldowns; daily rewards; invites; profile roles.

{% hint style="danger" %}
Cleanup is irreversible. See also [Wipe](../wipe.md).
{% endhint %}

### Role for all members

Grant or remove a Discord role (up to 500 members per request).

### Spawn wormhole

Instant spawn of an enabled wormhole.

### Role properties

Role inventory flags: Can remove; Cannot transfer / sell / giveaway / auction.

### Backups

Save or restore: items, achievements, quests, categories, gifts, income roles, wormholes, styles, profiles, jobs, permissions, promocodes, autogenerators.

## “Activities” tab

Drop table for fishing / mining / voice / messages:

| Field | Description |
| --- | --- |
| Item | What drops |
| Chance % | Sum of chances ≤ 100 |
| Min. / Max. | Quantity |
| Min. / Max. XP | For fishing and mining |

## “Cooldowns” tab

| Field | Description |
| --- | --- |
| Command cooldown | Command + seconds |
| Immune roles | Roles that skip command cooldown |
