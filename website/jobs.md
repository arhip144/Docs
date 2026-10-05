---
description: Configuring jobs (/work) on the site
icon: briefcase
---

# Jobs (website)

Path: `/dashboard/:guildId/jobs` → `/jobs/:jobId`

The player command `/work` requires [premium](../premium.md). Message variables: [Variables: jobs](../variables/jobs.md).

## Basic fields

| Field | Description |
| --- | --- |
| Job name | 2–30 characters |
| Emoji | Emoji |
| Enabled | Job is available |
| Hidden | Not shown in the list |
| Description | Up to 200 characters |

## “Action 1” and “Action 2” tabs

Each action has:

| Field | Description |
| --- | --- |
| Action name | Up to 20 characters |
| Action permission | [Permission](permissions.md) object |

### Success / Failure sub-tabs

| Field | Description |
| --- | --- |
| Success chance | % (on success tab) |
| Hide chance | Do not show to player |
| Messages | Up to 10 texts (up to 200 characters) |
| Images | Up to 10 URLs |
| Action cooldown (sec) | Up to 604800 (7 days); default 43200 |
| All jobs cooldown (sec) | Shared cooldown |
| Hide cooldowns / rewards | Toggles |
| Rewards | Up to 10: currency / XP / RP / item, min–max |

Discord: [Creating job](../guide/jobs.md).
