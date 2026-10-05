---
description: Guide to creating buttons that run the functionality of certain commands
icon: square-check
---

# Creating custom buttons

Discord buttons with bot actions (gift, purchase, quest, profile…). On the website it is easier to build messages in the [builder](../website/message-builder.md).

The main command for creating buttons is [/components](../commands/admins.md)

## Arguments of the [/components buttons add](../commands/admins.md) command:

|              Argument              |                          Description                          | Required |
| :--------------------------------: | :--------------------------------------------------------: | :----------: |
| message\_url |  Link to the message the button will be added to  |      Yes      |
|            style           |  <p>Button style:<br>Link - a link button<br></p>  |      Yes      |
|      id-or-url     | Button ID or a link to a resource (if the style is Link) |      Yes      |
|            row            |       The component row the button will be added to       |      Yes      |
|          column          |       The component column the button will be added to      |      Yes      |
|          label          |                       Button label                      |      No     |
|           emoji           |                        Button emoji                       |      No     |
|        disabled        |                  Whether the button will be disabled                 |      No     |

{% hint style="danger" %}
The "label" or "emoji" argument must be filled in
{% endhint %}

## Arguments of the [/components buttons remove](../commands/admins.md) command:

|              Argument              |                       Description                      | Required |
| :--------------------------------: | :-------------------------------------------------: | :----------: |
| message\_url | Link to the message the button will be removed from |      Yes      |
|            row            |     The component row the button will be removed from     |      Yes      |
|          column          |     The component column the button will be removed from    |      Yes      |

## Available button commands: <a href="#available-buttons" id="available-buttons"></a>

{% tabs %}
{% tab title="Get a gift" %}
ID: cmd{get-gift}gift{giftId}

Arguments:

| Name |  Description  | Required |
| :------: | :--------: | :----------: |
|   gift   | Gift ID |      Yes      |

[Guide to creating gifts](gifts.md)
{% endtab %}

{% tab title="Buy" %}
ID: cmd{buy}item{itemId}amount{10}price\_type{currency}price{10} prms-off dscnt-off limits-off

Arguments:

|   Name  |                        Description                        | Required |
| :---------: | :----------------------------------------------------: | :----------: |
|     item    |                       Item ID                      |      Yes      |
|    amount   |                 Amount to buy                 |      No     |
| price\_type | <p>Price: item ID;<br>currency - server currency</p> |      No     |
|    price    |                    Price: amount                    |      No     |
|   prms-off  |    Disables purchase permissions, if any    |      No     |
|  dscnt-off  |       Disables the reputation-based discount      |      No     |
|  limits-off |               Disables purchase limits              |      No     |
|  ignr-shop  |   Ignores the item's availability and amount in the shop  |      No     |

[Guide to creating items](items/)
{% endtab %}

{% tab title="Sell" %}
ID: cmd{sell}item{itemId}amount{10}

Arguments:

| Name |        Description        | Required |
| :------: | :--------------------: | :----------: |
|   item   |       Item ID      |      Yes      |
|  amount  | Amount to sell |      No     |

[Guide to creating items](items/)
{% endtab %}

{% tab title="Take a quest" %}
ID: cmd{quest-give-to-user}quest{questId}

Arguments:

| Name |                                                                                            Description                                                                                           | Required |
| :------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :----------: |
|   quest  | <p>Possible values:<br>1. Quest ID<br>2. active - get all active quests<br>3. daily - get a random daily quest<br>4. weekly - get a random weekly quest</p> |      Yes      |

[Guide to creating quests](quests.md)
{% endtab %}

{% tab title="Quest: claim reward" %}
ID: cmd{getQuestReward}quest{questId}

Arguments:

| Name |  Description | Required |
| :------: | :-------: | :----------: |
|   quest  | Quest ID |      No     |

If the **quest** argument is omitted, the user will receive the rewards from all quests.

[Guide to creating quests](quests.md)
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Cancel a quest" %}
ID: cmd{quest-take-from-user}quest{questId}

Arguments:

| Name |  Description | Required |
| :------: | :-------: | :----------: |
|   quest  | Quest ID |      Yes      |

[Guide to creating quests](quests.md)
{% endtab %}

{% tab title="Give an item" %}
ID: cmd{give-item}item{itemId}amount{10}usr{userId}

Arguments:

| Name |                                                      Description                                                      | Required |
| :------: | :----------------------------------------------------------------------------------------------------------------: | :----------: |
|   item   |                                                     Item ID                                                    |      Yes      |
|  amount  |                                               Amount to give                                               |      No     |
|    usr   | The user the item will be given to; if omitted, it is given to the user who pressed the button |      No     |

[Guide to creating items](items/)
{% endtab %}

{% tab title="Take an item" %}
ID: cmd{take-item}item{itemId}amount{10}usr{userId}

Arguments:

| Name |                                                      Description                                                     | Required |
| :------: | :---------------------------------------------------------------------------------------------------------------: | :----------: |
|   item   |                                                    Item ID                                                    |      Yes      |
|  amount  |                                               Amount to take                                              |      No     |
|    usr   | The user the item will be taken from; if omitted, it is taken from the user who pressed the button |      No     |

[Guide to creating items](items/)
{% endtab %}

{% tab title="Bot commands" %}
ID: cmd{help}commands eph reply

Arguments:

| Name |                            Description                           | Required |
| :------: | :-----------------------------------------------------------: | :----------: |
|    eph   |  If present, the message is visible only to the user who pressed the button  |      No     |
|   reply  | If present, the message is sent as a reply |      No     |
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Profile" %}
ID: cmd{profile} eph reply

Arguments:

| Name |                                                  Description                                                 | Required |
| :------: | :-------------------------------------------------------------------------------------------------------: | :----------: |
|    eph   |                        If present, the message is visible only to the user who pressed the button                        |      No     |
|   reply  |                       If present, the message is sent as a reply                       |      No     |
|    usr   |       ID of the user who can use the button; if omitted, anyone can use it      |      No     |
|    mbr   | ID of the user whose profile will be shown; if omitted, the profile of the user who pressed the button is shown |      No     |
{% endtab %}

{% tab title="Inventory" %}
ID: cmd{inventory} eph reply

Arguments:

<table><thead><tr><th width="216" align="center">Name</th><th width="299.66666666666663" align="center">Description</th><th align="center">Required</th></tr></thead><tbody><tr><td align="center">eph</td><td align="center">If present, the message is visible only to the user who pressed the button</td><td align="center">No</td></tr><tr><td align="center">reply</td><td align="center">If present, the message is sent as a reply</td><td align="center">No</td></tr><tr><td align="center">usr</td><td align="center">ID of the user who can use the button; if omitted, anyone can use it</td><td align="center">No</td></tr><tr><td align="center">mbr</td><td align="center">ID of the user whose inventory will be shown; if omitted, the inventory of the user who pressed the button is shown</td><td align="center">No</td></tr></tbody></table>
{% endtab %}

{% tab title="Achievements" %}
ID: cmd{achievements} eph reply

Arguments:

| Name |                                                        Description                                                       | Required |
| :------: | :-------------------------------------------------------------------------------------------------------------------: | :----------: |
|    eph   |                              If present, the message is visible only to the user who pressed the button                              |      No     |
|   reply  |                             If present, the message is sent as a reply                             |      No     |
|    usr   |             ID of the user who can use the button; if omitted, anyone can use it            |      No     |
|    mbr   | ID of the user whose achievements will be shown; if omitted, the achievements of the user who pressed the button are shown |      No     |
{% endtab %}

{% tab title="Rank" %}
ID: cmd{rank} eph reply

Arguments:

| Name |                                                      Description                                                     | Required |
| :------: | :---------------------------------------------------------------------------------------------------------------: | :----------: |
|    eph   |                            If present, the message is visible only to the user who pressed the button                            |      No     |
|   reply  |                           If present, the message is sent as a reply                           |      No     |
|    mbr   | ID of the user whose card will be shown; if omitted, the card of the user who pressed the button is shown |      No     |
{% endtab %}

{% tab title="Rank set" %}
ID: cmd{rank-set} eph reply

Arguments:

| Name |                            Description                           | Required |
| :------: | :-----------------------------------------------------------: | :----------: |
|    eph   |  If present, the message is visible only to the user who pressed the button  |      No     |
|   reply  | If present, the message is sent as a reply |      No     |
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Say" %}
ID: cmd{say}channelId{ID}messageId{ID}permission{ID} eph reply

Arguments:

|    Name    |                            Description                           | Required |
| :--------: | :-----------------------------------------------------------: | :----------: |
|     eph    |  If present, the message is visible only to the user who pressed the button  |      No     |
|    reply   | If present, the message is sent as a reply |      No     |
|   update   |         If present, the message will be edited         |      No     |
|  channelId |                 ID of the channel to look up the message in                |      No     |
|  messageId |                          Message ID                         |      No     |
| permission |                            Permission ID                           |      No     |

{% hint style="info" %}
The channelId and messageId arguments are used together; you cannot use only one of them
{% endhint %}

{% hint style="info" %}
The channelId and messageId arguments are used to output a message from a specific channel. This way you can create a button that outputs any message from any channel.
{% endhint %}

{% file src="../.gitbook/assets/Видео 17-06-2023 11_26_02.mp4" %}

{% hint style="info" %}
A message output through the channelId and messageId arguments includes the buttons and files attached to that message.
{% endhint %}

{% hint style="info" %}
If you paste a message link into the say command form, the bot will output a full copy of the message.
{% endhint %}

{% file src="../.gitbook/assets/Видео 17-06-2023 11_36_45.mp4" %}
{% endtab %}

{% tab title="Stats" %}
ID: cmd{stats} eph reply

Arguments:

| Name |                                                     Description                                                    | Required |
| :------: | :-------------------------------------------------------------------------------------------------------------: | :----------: |
|    eph   |                           If present, the message is visible only to the user who pressed the button                           |      No     |
|   reply  |                          If present, the message is sent as a reply                          |      No     |
|    usr   |          ID of the user who can use the button; if omitted, anyone can use it         |      No     |
|    mbr   | ID of the user whose stats will be shown; if omitted, the stats of the user who pressed the button are shown |      No     |
{% endtab %}

{% tab title="Role inventory" %}
ID: cmd{inventory-roles} eph reply

Arguments:

<table><thead><tr><th width="216" align="center">Name</th><th width="299.66666666666663" align="center">Description</th><th align="center">Required</th></tr></thead><tbody><tr><td align="center">eph</td><td align="center">If present, the message is visible only to the user who pressed the button</td><td align="center">No</td></tr><tr><td align="center">reply</td><td align="center">If present, the message is sent as a reply</td><td align="center">No</td></tr><tr><td align="center">usr</td><td align="center">ID of the user who can use the button; if omitted, anyone can use it</td><td align="center">No</td></tr><tr><td align="center">mbr</td><td align="center">ID of the user whose role inventory will be shown; if omitted, the role inventory of the user who pressed the button is shown</td><td align="center">No</td></tr></tbody></table>
{% endtab %}

{% tab title="Create a custom role" %}
ID: cmd{custom-role}
{% endtab %}
{% endtabs %}
