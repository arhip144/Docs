---
description: What's it? What are they for? How do I create it?
---

# 🌀 Wormholes

## What are wormholes?

These are events that appear in a certain channel at a certain moment

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>An example of a wormhole with <a href="styles.md">style</a></p></figcaption></figure>

## What are wormholes for?

This is one of the many ways to get items, currency, experience, reputation

## How wormholes are works?

As soon as the wormhole appears, you have a chance to take all the items from it. By chance, it means that after a while it may disappear or another user may take it.

## Creating a Wormhole

To create a wormhole, run the command [/manager-wormholes create \<name>](../commands/admins.md)

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

In this panel, we configure:

* Style (not required) - a [guide to creating a style](styles.md)
* Item - the item that will drop out (Item/currency/experience/Reputation)
* Chance - chance of spawn from 1% to 100%
* Webhook - a webhook that will send a message
* Amount - the minimum and maximum amount of dropped item/currency/experience/reputation
* Lifetime - the lifetime of the wormhole in the channel
* Cron-pattern - [examples of patterns and an explanation of what they are](cron-patterns.md)
* The number of spawns - after the expiration, the wormhole will turn off

After all the settings, you need to turn on the wormhole

{% hint style="info" %}
To see what a wormhole will look like, you can execute the command [/wormhole-spawn \<name>](../commands/admins.md)
{% endhint %}

{% content-ref url="styles.md" %}
[styles.md](styles.md)
{% endcontent-ref %}

## Editing the wormhole

To edit the wormhole, run the command [/manager-wormholes edit \<name>](../commands/admins.md)

## Copying a Wormhole

To copy a wormhole, run the command [/manager-wormholes copy \<wormhole> \<name for new wormhole>](../commands/admins.md)

## Deleting the wormhole

To delete a wormhole, run the command [/manager-wormholes delete](../commands/admins.md)

## View all wormholes

To view all wormholes, run the command [/manager-wormholes view](../commands/admins.md)

## Viewing wormhole information (public command)

To view information about a specific wormhole, run the command [/wormhole \<name>](../commands/general.md)

## Thematic achievements

1. Touch the wormhole N times
2. Spawn the wormhole N times

{% content-ref url="achievements.md" %}
[achievements.md](achievements.md)
{% endcontent-ref %}

## Thematic tasks for quests

1. Touch the wormhole N times
2. Spawn the wormhole N times

{% content-ref url="quests.md" %}
[quests.md](quests.md)
{% endcontent-ref %}
