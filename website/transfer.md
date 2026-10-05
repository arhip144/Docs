---
description: Export and import server configuration
icon: file-export
---

# Export and import (website)

Path: `/dashboard/:guildId/transfer`

{% hint style="warning" %}
Available only to **dashboard administrators** (server owner, Administrator, manage access).
{% endhint %}

Lets you save server settings and content to JSON and load it back.

## Content types

Match dashboard sections (except administration): items, achievements, categories, gifts, permissions, promocodes, quests, jobs, income roles, styles, wormholes, autogenerators, bonus channels, message builder, server settings.

Importing **permissions**, **gifts**, and **autogenerators** requires [premium](../premium.md).

## Export

1. Select types (or “Select all”).
2. Click **Download JSON**.

## Import

1. Choose an export file.
2. Mark content types.
3. Mode:
   - **Merge** — add/update without full wipe;
   - **Replace** — delete selected types on the server, then import.
4. If needed, map **income roles** and **bonus channels** to roles/channels on the current server (rows without a choice are skipped).
5. Confirm import.

The report shows: created / updated / frozen / deleted, warnings, and errors.
