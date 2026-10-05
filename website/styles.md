---
description: Wormhole appearance styles on the site
icon: palette
---

# Wormhole styles (website)

Path: `/dashboard/:guildId/styles` → `/styles/:styleId`

{% hint style="info" %}
Limit: **5** without premium, **25** with premium.
{% endhint %}

## Basic fields

| Field | Description |
| --- | --- |
| Name | Style name |

## “Spawn” and “Claim” tabs

Same embed fields for spawn moment and claim moment:

| Field | Description |
| --- | --- |
| Description | Embed text |
| Title | Title |
| Author / Author icon | Author |
| Footer / Footer icon | Footer |
| Thumbnail | Thumbnail URL |
| Image | Image URL |
| Color | HEX; option “use item color” |
| Button | Button text |
| Button style | Primary / Secondary / Success / Danger |
| Button emoji | Emoji |

### Placeholders

Spawn: `{item_emoji}`, `{item_name}`, `{item_image}`, `{item_color}`, `{member_name}`, `{member_avatar}`.

Claim: same + `{member_color}`, `{amount}`.

Full list: [Variables: wormholes styles](../variables/styles.md).

Discord: [Creation of wormholes styles](../guide/styles.md).
