---
description: Guide to creating gifts on the server
icon: gift
---

# Create gifts (manager-gifts)

The main command for managing gifts - /manager-gifts

## ✔️Menu: Edit <img src="../.gitbook/assets/Скриншот 07-02-2023 230810.png" alt="" data-size="original">

* Comment - after receiving the gift, the user will see this comment.![](<../.gitbook/assets/Скриншот 07-02-2023 233016.png>)
* Thumbnail - displayed in the upper right corner after receiving the gift\
  ![](<../.gitbook/assets/fsdfs (3).png>)
* Image - displayed at the bottom after receiving the gift\
  ![](<../.gitbook/assets/159Z\_2107.w026.n002.628B.p1.628 \[преобразованныfsdй]-01.png>)
* Frame color - the color is displayed from the left edge of the embed after receiving the gift
* The maximum number of unique users is the number of people who will be able to receive a gift
* Number of gift receipts - how many times one person will be able to receive a gift
* Cooldown - the time in seconds after which it will be possible to receive a gift again
* Start and end dates - the dates during which it will be possible to receive a gift
* Turn Off / On - allows you to turn on and off the gift, in the off state - it will not be able to receive

## ✔️Button: Permissions

Allows you to select an existing preset of permissions\\

## ✔️Button: Members![](<../.gitbook/assets/Скриншот 07-02-2023 231156.png>)

Allows you to edit members for this gift: set/delete the date of the last receipt, the number of receipts for any user\
<img src="../.gitbook/assets/Скриншот 07-02-2023 233244.png" alt="" data-size="original">

## ✔️Button: Items ![](<../.gitbook/assets/Скриншот 07-02-2023 231307.png>)

Allows you to delete/edit/add items as a gift

The item ID can include the following parameters

* xp - experience
* currency - server currency
* rp - reputation
* ID of any item

![](<../.gitbook/assets/Скриншот 07-02-2023 233506.png>)

{% hint style="info" %}
### ✔️How do I create a button with a generated ID?

1. You need to execute the command /components buttons add
2. The message\_url argument (link\_to\_message): Insert a link to a BOT message (can be generated using the /embed-generator or /say command) for which you want to attach a button
3. The "style" argument: Choose any style except Link
4. id\_or\_url argument (id\_or\_link): Insert previously generated ID
5. Arguments row, column (row, column): Select the location of the button
6. Label, emoji arguments (name, emoji): Choose emoji and text for the button
7. Execute the command<img src="../.gitbook/assets/Скриншот 07-02-2023 231601.png" alt="" data-size="line">

After the listed items, the bot will attach the button to the message. <img src="../.gitbook/assets/Скриншот 07-02-2023 232118.png" alt="" data-size="original">
{% endhint %}

<figure><img src="../.gitbook/assets/fsdfs (2).png" alt=""><figcaption></figcaption></figure>
