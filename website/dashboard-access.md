---
description: How dashboard access and per-section roles work
icon: shield-halved
---

# Dashboard and access

## Dashboard hub

Path: `/dashboard/:guildId`

The hub shows section cards. You only see sections you can access. The hub also includes:

| Card | Who sees it | Description |
| --- | --- | --- |
| Sections below | By roles / admins | Items, quests, settings… |
| Premium | Anyone with dashboard access | Status and premium purchase |
| Export and import | Dashboard admins only | Move configuration |

## Who counts as a dashboard administrator

Full access to all sections, access management, and export/import:

- bot owner;
- server owner;
- members with Discord **Administrator**;
- members with the manage-dashboard-access flag (`canManageDashboardAccess`).

## Sections with role-based access

An administrator can assign Discord roles to each section (**Dashboard access** modal). For each section — multi-select “Roles with dashboard access” (up to 25 roles).

| Key | UI name |
| --- | --- |
| `items` | Items |
| `achievements` | Achievements |
| `categories` | Shop categories |
| `gifts` | Gifts |
| `permissions` | Permissions |
| `promocodes` | Promocodes |
| `quests` | Quests |
| `jobs` | Jobs |
| `incomeRoles` | Income roles |
| `styles` | Wormhole styles |
| `wormholes` | Wormholes |
| `autogenerators` | Promocode autogen. |
| `bonusChannels` | Bonus channels |
| `messageBuilder` | Message builder |
| `settings` | Server settings |
| `moderation` | Administration |

{% hint style="info" %}
The legacy format (one flat role list) is treated as the same access to all sections.
{% endhint %}

## Special pages

| Page | Access |
| --- | --- |
| [Export and import](transfer.md) | Dashboard administrators only |
| [Premium](premium.md) | Any user with dashboard access |
| [Message builder](message-builder.md) | Public `/embed`; in dashboard access — separate section |

## If a section is unavailable

- Check your Discord role and access settings on the hub.
- Ask the server owner or an administrator to grant a role for the section.
- For gifts, permissions, and autogenerators, [premium](../premium.md) is also required to create objects.
