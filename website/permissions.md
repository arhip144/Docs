---
description: Permission presets (access conditions) on the site
icon: key
---

# Permissions (website)

Path: `/dashboard/:guildId/permissions` → `/permissions/:permissionId`

{% hint style="warning" %}
Creating permissions requires [premium](../premium.md). Presets are used in items, quests, gifts, promocodes, and more.
{% endhint %}

## Basic fields

| Field | Description |
| --- | --- |
| Name | 2–30 characters |
| Enabled | Preset is active |
| Test | Check conditions on yourself |

## Requirements

Up to 10 conditions. Types:

| Type | Description |
| --- | --- |
| Roles | hasAll / hasAny / except (up to 25 roles) |
| Item in inventory | Required item |
| Achievement completed / not completed | Achievement |
| Channels | Up to 10 channels |
| Quest completed | Quest |
| Time (UTC) | Time range |
| Days of week | Sunday–Saturday |
| On server (minutes) | MemberSince |
| Level / seasonal level / XP | Numeric thresholds |
| Voice session metrics | Session XP/RP/hours/currency |
| Messages, hours, RP, likes, currency… | Statistics |
| XP/RP/CUR/Luck booster (%) | Booster active |
| Day/week/month/year stats | XP, messages, hours, RP, likes, currency, invites, bumps, giveaways, wormholes, quests, market |

Discord: [Permissions](../guide/permissions.md).
