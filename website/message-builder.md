---
description: Message and embed builder on the site
icon: pen-to-square
---

# Message builder (website)

Path: `/embed` (public tool)

Build a Discord message (classic embeds or Components V2), save to the library, and send via bot or webhook.

## Modes

| Mode | Description |
| --- | --- |
| Embeds | Classic Discord embeds |
| Containers | Components V2 (containers, sections, galleries) |

## Classic embed

| Field | Description |
| --- | --- |
| Message text | Content above embed |
| Title / Title link | Title |
| Description | Description |
| Sidebar color | HEX |
| Timestamp | Timestamp |
| Author / link / icon | Author |
| Footer / icon | Footer |
| Thumbnail / Image | URL |
| Fields | Name, value, “inline” |
| Webhook name / avatar | When sending via webhook |

## Components V2

Container (accent color, spoiler), text, separator, gallery, section, buttons.

## Buttons

| Field | Description |
| --- | --- |
| Text | Label |
| Style | Primary / Secondary / Success / Danger / Link |
| Button command | Bot action (see below) |
| Flags | Ephemeral, reply, etc. |

### Button commands (examples)

Claim gift; Buy; Sell; Take quest; Quest: claim reward; Cancel quest; Grant / remove item; Bot commands (help); Profile; Inventory; Achievements; Rank; custom customId.

Full button actions also in [Creating custom buttons](../guide/buttons.md).

## Library and send

| Feature | Description |
| --- | --- |
| Local / On server | Where to store templates |
| Folders | Organization |
| Save / load | Templates |
| Send / edit | New message or edit |
| Custom webhook / Bot / Bot webhook | Send method (sign-in required) |
| JSON import/export | Share configuration |
| Discord import | Import from a Discord message |
