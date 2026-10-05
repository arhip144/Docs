---
description: How to sign in to the site with Discord and open the server list
icon: right-to-bracket
---

# Login and my servers

## Sign in

1. On any page, click **Log in** in the header.
2. Discord OAuth opens. The bot requests:
   - `identify` — who you are;
   - `guilds` — the list of servers you are on.
3. After a successful sign-in you return to the previous page or to **/servers** (My servers).

The `/login` page handles Discord’s response. If the window opened as a popup, you can close it after sign-in succeeds.

{% hint style="warning" %}
Without signing in, the dashboard, server profile, market, leaderboard, and crash are unavailable.
{% endhint %}

## My servers

Path: `/servers`

The page shows Discord servers where:

- WETBOT is added, or
- you have Manage Guild / Administrator.

### List features

| Element | Description |
| --- | --- |
| Search | Filter servers by name |
| Favorites | Pin frequently used servers |
| Server card | Icon, name; click opens the dashboard |

Clicking a server opens the dashboard hub: `/dashboard/:guildId`.

## Sign out

Choose sign out in the user menu — the session is cleared and you are returned to the home page.

## If a server is missing

1. Make sure the bot is invited: [https://wetbot.space/invite](https://wetbot.space/invite).
2. Check that your Discord account is on the server.
3. Sign out and sign in again to refresh the OAuth guild list.
