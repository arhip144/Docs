---
description: What are they? What are they for? How do you create them?
icon: hurricane
---

# Wormholes

{% hint style="info" %}
Limit: **5** without premium, **100** with premium. Full UI fields: [Wormholes on the website](../website/wormholes.md).
{% endhint %}

## What are wormholes?

They are events that appear at a certain moment in a certain channel

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption><p>Example of a wormhole with a <a href="styles.md">style</a></p></figcaption></figure>

## What are wormholes for?

They are one of many ways to obtain items, currency, experience, and reputation

## How do wormholes work?

As soon as a wormhole appears, you have a chance to grab all the items from it. By "chance" we mean that after some time it may disappear, or another user may take it.

## Creating a wormhole

To create a wormhole, run the command [/manager-wormholes create <wormhole name>](../commands/admins.md)

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

In this manager you configure:

| Field | Description |
| --- | --- |
| Style | Optional; [creating a style](styles.md) |
| Item | Reward: item / currency / experience / reputation |
| Chance | Spawn chance up to 100% |
| Webhook / channel | Where the message is sent |
| Amount | Min. and max. reward |
| Lifetime | Seconds until it disappears |
| Cron pattern | [Cron reference](cron-patterns.md) |
| Number of spawns | After they run out, the wormhole is disabled |
| Permission | Who can take it |
| Delete after collection / show date | Message behavior |

After all the settings, enable the wormhole

{% hint style="info" %}
To see what a wormhole will look like, use the command [/wormhole-spawn <wormhole name>](../commands/admins.md)
{% endhint %}

{% content-ref url="styles.md" %}
[styles.md](styles.md)
{% endcontent-ref %}

## Editing a wormhole

To edit a wormhole, run the command [/manager-wormholes edit <wormhole name>](../commands/admins.md)

## Copying a wormhole

To copy a wormhole, run the command [/manager-wormholes copy <wormhole> <new wormhole name>](../commands/admins.md)

## Deleting a wormhole

To delete a wormhole, run the command [/manager-wormholes delete <wormhole name>](../commands/admins.md)

## Viewing all wormholes

To view all wormholes, run the command [/manager-wormholes view](../commands/admins.md)

## Viewing wormhole information (public command)

To view information about a specific wormhole, run the command[ /wormhole <wormhole name>](../commands/general.md)

## Related achievements

1. Touch a wormhole N times
2. Spawn a wormhole N times

{% content-ref url="achievements.md" %}
[achievements.md](achievements.md)
{% endcontent-ref %}

## Related quest tasks

1. Use a wormhole N times
2. Spawn a wormhole N times

{% content-ref url="quests.md" %}
[quests.md](quests.md)
{% endcontent-ref %}
