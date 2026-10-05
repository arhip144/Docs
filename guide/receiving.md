---
icon: plus-large
description: Setting up rewards for activity
---

# Earning currency, experience, reputation

## What is this?

Base rewards for messages, voice, invites, bumps, likes, and the first discovery of an item. [Bonus channels](bonuses.md) and [luck](../rp-luck.md) also have an effect.

## Discord

Run [/manager-settings](../commands/admins.md) → **Earning currency, experience, reputation**.

<figure><img src="../.gitbook/assets/изображение_2022-10-20_182438085.png" alt=""><figcaption></figcaption></figure>

**Level factor** (for example 10): each new level requires N more experience than the previous one to reach the next.

| Source | Rules |
| --- | --- |
| Per message | In text channels that are not excluded (muted ones are set in the channel settings) |
| Per voice activity | Per minute; more than 1 person with a microphone; bots don't count; muted users don't count |
| Per invite | Requires the bot's "Manage Server" permission |
| Per bump | `/bump`, `/up`, `/like` of other bots (rewards are premium) |
| Per like | `/like`; both sides receive the reward |
| Per item found for the first time | The first discovery of an item |

{% hint style="success" %}
When the level factor changes, the bot recalculates users' levels.
{% endhint %}

Level roles and daily rewards are also in the settings; see [Setting up the bot](settings.md).

## On the website

{% content-ref url="../website/settings/activities-channels.md" %}
[activities-channels.md](../website/settings/activities-channels.md)
{% endcontent-ref %}
