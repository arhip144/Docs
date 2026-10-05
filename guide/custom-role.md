---
description: Premium is required to create custom roles
icon: masks-theater
---

# Creating a custom role

## What is this?

Members create their own Discord roles (color, name) with the `/custom-role` command. The role goes to the [role inventory](inventory-roles.md).

{% hint style="warning" %}
[Premium](../premium.md) is required.
{% endhint %}

## Discord: initial setup

Enter [/manager-settings](../commands/admins.md) → the **Custom roles** section.

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

| Parameter | Description |
| --- | --- |
| Position / create under a role | Without a reference role, `/custom-role` is unavailable |
| Moderation channel | If set, requests go to moderation; otherwise the role is created immediately |
| Permission for custom roles | A [permission](permissions.md) preset |
| Display separately / temporary | Hoist and timed roles |
| Minimum minutes / creation limit | Restrictions |

If there is a moderation channel, staff review the requests. Without a channel, roles are given to the inventory automatically.

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

Player command: [/custom-role](../commands/general.md).

Creation can be moved [to a button](buttons.md#create-a-custom-role).

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

## On the website

{% content-ref url="../website/settings/custom-boosters.md" %}
[custom-boosters.md](../website/settings/custom-boosters.md)
{% endcontent-ref %}
