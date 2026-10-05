---
description: Guide to creating gifts on the server
icon: gift
---

# Creating gifts (manager-gifts)

{% hint style="warning" %}
Gifts require [premium](../premium.md).
{% endhint %}

The main command for managing gifts is [/manager-gifts](../commands/admins.md)

CRUD: `create` / `edit` / `copy` / `delete` / `view` (see [admin commands](../commands/admins.md)).

## ✔️Menu: Edit <img src="../.gitbook/assets/Скриншот 07-02-2023 230810.png" alt="" data-size="original">

* Comment - after receiving the gift, the user will see this comment. ![](<../.gitbook/assets/Скриншот 07-02-2023 233016.png>)
* Thumbnail - displayed in the top right corner after receiving the gift\
  ![](<../.gitbook/assets/fsdfs (3).png>)
* Image - displayed at the bottom after receiving the gift\
  ![](<../.gitbook/assets/159Z\_2107.w026.n002.628B.p1.628 \[преобразованныfsdй]-01.png>)
* Border color - the color shown on the left edge of the embed after receiving the gift
* Maximum unique users - the number of people who will be able to receive the gift
* Number of gift claims - how many times one person can receive the gift
* Cooldown - time in seconds after which the gift can be received again
* Start and end dates - the dates during which the gift can be received
* Level - the range of levels that can receive the gift
* Disable/Enable - lets you turn the gift on and off; while it is disabled, it cannot be received

## ✔️Button: Permissions&#x20;

Lets you select an existing permission preset

## ✔️Button:  Users ![](<../.gitbook/assets/Скриншот 07-02-2023 231156.png>)

Lets you edit users for this gift: set/remove the date of the last claim and the number of claims for any user\
<img src="../.gitbook/assets/Скриншот 07-02-2023 233244.png" alt="" data-size="original">

## ✔️Button: Items ![](<../.gitbook/assets/Скриншот 07-02-2023 231307.png>)

Lets you remove/edit/add items in the gift

The item ID can take the following values

* xp - experience
* currency - server currency
* rp - reputation
* the ID of any item

![](<../.gitbook/assets/Скриншот 07-02-2023 233506.png>)

{% hint style="info" %}
## ✔️How do you create a button with a generated ID?

1. Run the command [/components buttons add](../commands/admins.md)
2. Argument `message_url`: Paste the link to the BOT's message (you can generate one with the [`/embed-generator`](../commands/admins.md) or [`/say`](../commands/admins.md) command) that you want to attach the button to
3. Argument `style`: Choose any style except Link
4. Argument `id_or_url`: Paste the previously generated ID
5. Arguments `row`, `column`: Choose the button's position
6. Arguments `label`, `emoji`: Choose an emoji and text for the button
7. Run the command <img src="../.gitbook/assets/Скриншот 07-02-2023 231601.png" alt="" data-size="line">

After these steps, the bot will attach the button to the message. <img src="../.gitbook/assets/Скриншот 07-02-2023 232118.png" alt="" data-size="original">
{% endhint %}

<figure><img src="../.gitbook/assets/fsdfs (2).png" alt=""><figcaption></figcaption></figure>

## On the website

{% content-ref url="../website/gifts.md" %}
[gifts.md](../website/gifts.md)
{% endcontent-ref %}

Gift buttons can also be built in the [message builder](../website/message-builder.md).
