---
description: Creating and editing quests on the site
icon: scroll
---

# Quests (website)

Path: `/dashboard/:guildId/quests` → `/quests/:questId`

{% hint style="info" %}
Limit: **5** without premium, **1000** with premium. Up to 5 tasks and 5 rewards per quest.
{% endhint %}

## Basic fields

| Field | Description |
| --- | --- |
| Name | 2–30 characters |
| Emoji | Quest emoji |
| Enabled | Quest is available |
| Active | Participates in rotation/granting |
| Description | Up to 1024 characters |
| Color | Embed color |
| Image | URL |
| Type | Daily / Weekly / Community / Repeatable |
| Completion condition | All tasks / Any task |

## “Tasks” tab

Up to 5 targets. Each has:

| Field | Description |
| --- | --- |
| Task type | See list below |
| Amount | Threshold |
| Object | Channel / user / item / quest / wormhole / promocode (if needed) |
| Custom description | Custom task text |
| Progress bar | Show progress |
| Optional task | Not required to finish; can set separate rewards |

### Task types

Send messages; minutes in voice; likes; invites; bump; earn/spend currency; fishing/mining; daily reward; wormhole; complete quests; create giveaway; market (sell); open/obtain/craft/use/buy/sell items; spawn wormhole; levels/XP; drop/transfer items; seasonal level/XP; promocode; transfer items to NPC.

## “Rewards” tab

Up to 5: XP / Reputation / Currency / Item / Role / Achievement. For roles — duration in minutes.

## “Next quests” tab

Up to 3 quests granted after completion.

## “Actions” tab

Mass/personal grant and removal, progress editing.

## “Permissions” tab

| Field | Description |
| --- | --- |
| Permission to take quest | [Permission](permissions.md) object |
| Permission to claim reward | Permission object |

Discord: [Creation of quests](../guide/quests.md).
