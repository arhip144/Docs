---
description: wetbot.space documentation — dashboard, profile, market, and tools
icon: globe
---

# wetbot.space website

[https://wetbot.space](https://wetbot.space/) is the web interface for the WETBOT bot. On the site you can manage server economy, configure items and quests, moderate members, open profiles, play crash, and build messages in the message builder.

## What’s on the site

| Section | For whom | Description |
| --- | --- | --- |
| [Login and servers](login-servers.md) | Everyone | Sign in with Discord and browse your servers |
| [Dashboard](dashboard-access.md) | Admins / roles with access | Dashboard section hub and access settings |
| Dashboard sections | Admins / roles with access | Items, quests, settings, and more |
| [Profile](profile.md) | Members | Customization, privacy, inventory |
| [Market](market.md) | Members | Player-to-player item and role listings |
| [Leaderboard](leaderboard.md) | Members | Leaderboards |
| [Crash](crash.md) | Members | Multiplier mini-game |
| [Message builder](message-builder.md) | Everyone | Embeds, Components V2, buttons |
| [Command catalog](commands-page.md) | Everyone | Search bot slash commands |

## Quick start

1. Open [wetbot.space](https://wetbot.space/) and click **Log in**.
2. Authorize with Discord (scopes `identify` and `guilds`).
3. Go to **My servers** and pick a server where the bot is present.
4. Open **Dashboard** — if you have administrator rights or a role with access to a section.

{% hint style="info" %}
Invite the bot: [https://wetbot.space/invite](https://wetbot.space/invite)
{% endhint %}

## Dashboard map

| Section | Path | Documentation |
| --- | --- | --- |
| Items | `/dashboard/:guildId/items` | [Items](items.md) |
| Achievements | `.../achievements` | [Achievements](achievements.md) |
| Shop categories | `.../categories` | [Categories](categories.md) |
| Gifts | `.../gifts` | [Gifts](gifts.md) |
| Permissions | `.../permissions` | [Permissions](permissions.md) |
| Promocodes | `.../promocodes` | [Promocodes](promocodes.md) |
| Quests | `.../quests` | [Quests](quests.md) |
| Jobs | `.../jobs` | [Jobs](jobs.md) |
| Income roles | `.../roles` | [Income roles](income-roles.md) |
| Wormhole styles | `.../styles` | [Styles](styles.md) |
| Wormholes | `.../wormholes` | [Wormholes](wormholes.md) |
| Promocode autogen. | `.../autogenerators` | [Autogenerators](autogenerators.md) |
| Bonus channels | `.../channels` | [Bonus channels](bonus-channels.md) |
| Server settings | `.../settings` | [Settings](settings.md) |
| Administration | `.../moderation` | [Administration](moderation.md) |
| Export and import | `.../transfer` | [Export and import](transfer.md) |
| Premium | `.../premium` | [Premium on the site](premium.md) |

## Connection to Discord

Most dashboard sections mirror Discord managers (`/manager-items`, `/manager-quests`, etc.). Full field tables are documented here on the site. The [guide](../guide/settings.md) covers workflows via Discord commands and concepts.

{% content-ref url="../premium.md" %}
[premium.md](../premium.md)
{% endcontent-ref %}
