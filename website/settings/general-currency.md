---
description: “General” and “Currency” tabs in server settings
icon: coins
---

# General and currency

Path: `/dashboard/:guildId/settings` → **General** / **Currency** tabs.

## General

| Field | Description |
| --- | --- |
| Bot language | `Русский`, `English`, `Українська`, `Español` |
| Premium | View-only status (purchase on [Premium](../premium.md) page) |

## Currency

| Field | Description |
| --- | --- |
| Name | Display name of server currency |
| Description | Text about the currency |
| Currency emoji | Standard or custom (custom — with premium) |
| Disable transfer | Blocks `/transfer` for currency |
| Disable drop | Blocks `/drop` for currency |
| Disable in crash | Cannot bet currency in crash |
| Transfer permission | [Permission](../permissions.md) object for transfer |
| Drop permission | Permission object for drop |

Discord: [Setting up the server currency](../../guide/currency.md).
