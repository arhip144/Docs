---
description: A guide to creating buttons with the functionality of some commands
---

# 🆒 Create custom buttons

The main command for creating buttons /components

### Arguments of the /components buttons add command:

|   Argument   |                               Description                              | Required |
| :----------: | :--------------------------------------------------------------------: | :------: |
| message\_url |         Link to the message for which the button will be added         |    Yes   |
|     style    |                              Button style                              |    Yes   |
|   id-or-url  | The ID of the button or a link to the resource (If the style is a Link |    Yes   |
|      row     |         The row of the component where the button will be added        |    Yes   |
|    column    |         Column of the component where the button will be added         |    Yes   |
|     label    |                              Button label                              |    No    |
|     emoji    |                              Button emoji                              |    No    |
|   disabled   |                      Will the button be turned off                     |    No    |

{% hint style="danger" %}
The arguments "label" or "emoji" are required
{% endhint %}

### Arguments of the /components buttons remove command:

|   Argument   |                          Description                         | Required |
| :----------: | :----------------------------------------------------------: | :------: |
| message\_url |    Link to the message in which the button will be removed   |    Yes   |
|      row     |   The row of the component where the button will be removed  |    Yes   |
|    column    | The column of the component where the button will be removed |    Yes   |

## Доступные команды для кнопок:

{% tabs %}
{% tab title="Get gift" %}
ID: cmd{get-gift}gift{giftId}

Arguments:

| Name | Description | Required |
| :--: | :---------: | :------: |
| gift |   Gift ID   |    Yes   |

[A guide to creating gifts](gifts.md)
{% endtab %}

{% tab title="Buy" %}
ID: cmd{buy}item{itemId}amount{10}price\_type{currency}price{10} prms-off dscnt-off limits-off

Arguments:

|     Name    |                        Description                        | Required |
| :---------: | :-------------------------------------------------------: | :------: |
|     item    |                          Item ID                          |    Yes   |
|    amount   |                    Amount for purchase                    |    No    |
| price\_type |   Price: Item ID; currency - the currency of the server   |    No    |
|    price    |                       Price: Amount                       |    No    |
|   prms-off  |           Disables purchase permissions, if any           |    No    |
|  dscnt-off  |         Disables discount depending on reputation         |    No    |
|  limits-off |                  Disables purchase limits                 |    No    |
|  ignr-shop  | Ignores the presence and quantity of the item in the shop |    No    |

[A guide to creating items](items.md)
{% endtab %}

{% tab title="Sell" %}
ID: cmd{sell}item{itemId}amount{10}

Arguments:

|  Name  |    Description    | Required |
| :----: | :---------------: | :------: |
|  item  |      Item ID      |    Yes   |
| amount | Quantity for sale |    No    |

[A guide to creating items](items.md)
{% endtab %}

{% tab title="Take quest" %}
ID: cmd{quest-give-to-user}quest{questId}

Arguments:

|  Name |                                                                                      Description                                                                                      | Required |
| :---: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :------: |
| quest | <p>Possible values:</p><ol><li>Quest ID</li></ol><ol><li>active - get all active quests</li><li>daily - get a random daily quest</li><li>weekly - get a random weekly quest</li></ol> |    Yes   |

[A guide to creating quests](quests.md)
{% endtab %}

{% tab title="Quest: get reward" %}
ID: cmd{getQuestReward}quest{questId}

Arguments:

|  Name | Description | Required |
| :---: | :---------: | :------: |
| quest |   Quest ID  |    No    |

In the absence of the quest argument, the user will receive rewards from all quests.

[A guide to creating quests](quests.md)
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Cancel quest" %}
ID: cmd{quest-take-from-user}quest{questId}

Arguments:

|  Name | Description | Required |
| :---: | :---------: | :------: |
| quest |   Quest ID  |    Yes   |

[A guide to creating quests](quests.md)
{% endtab %}

{% tab title="Give item" %}
ID: cmd{give-item}item{itemId}amount{10}usr{userId}

Arguments:

|  Name  |                                                   Description                                                  | Required |
| :----: | :------------------------------------------------------------------------------------------------------------: | :------: |
|  item  |                                                     Item ID                                                    |    Yes   |
| amount |                                                 Amount for sale                                                |    No    |
|   usr  | The user for whom the item will be issued, if it is missing, it will be issued to the user who used the button |    No    |

[A guide to creating items](items.md)
{% endtab %}

{% tab title="Take item" %}
ID: cmd{take-item}item{itemId}amount{10}usr{userId}

Arguments:

|  Name  |                                                Description                                                | Required |
| :----: | :-------------------------------------------------------------------------------------------------------: | :------: |
|  item  |                                                ID предмета                                                |    Yes   |
| amount |                                              Amount for sale                                              |    No    |
|   usr  | The user from whom the item will be removed, if absent, will be removed from the user who used the button |    No    |

[A guide to creating items](items.md)
{% endtab %}

{% tab title="Bot commands" %}
ID: cmd{help}commands eph reply

Arguments:

|  Name |                                       Description                                       | Required |
| :---: | :-------------------------------------------------------------------------------------: | :------: |
|  eph  | If there is, then the message will be visible only to the person who pressed the button |    No    |
| reply |                If there is, the message will be sent as a reply message.                |    No    |
|       |                                                                                         |          |
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Profile" %}
ID: cmd{profile}eph reply

Arguments:

|  Name |                                                        Description                                                       | Required |
| :---: | :----------------------------------------------------------------------------------------------------------------------: | :------: |
|  eph  |                  If there is, then the message will be visible only to the person who pressed the button                 |    No    |
| reply |                                 If there is, the message will be sent as a reply message.                                |    No    |
|  usr  |                          The ID of the user who can use the button, if not, everyone can use it                          |    No    |
|  mbr  | The ID of the user whose profile will be displayed, if absent, the profile of the user who used the button is displayed. |    No    |
{% endtab %}

{% tab title="Inventory" %}
ID: cmd{inventory}eph reply

Arguments:

|  Name |                                                          Description                                                          | Required |
| :---: | :---------------------------------------------------------------------------------------------------------------------------: | :------: |
|  eph  |                    If there is, then the message will be visible only to the person who pressed the button                    |    No    |
| reply |                                   If there is, the message will be sent as a reply message.                                   |    No    |
|  usr  |                             The ID of the user who can use the button, if not, everyone can use it                            |    No    |
|  mbr  | The ID of the user whose inventory will be displayed, if missing, the inventory of the user who used the button is displayed. |    No    |
{% endtab %}

{% tab title="Achievements" %}
ID: cmd{achievements}eph reply

Arguments:

|  Name |                                                         Description                                                         | Required |
| :---: | :-------------------------------------------------------------------------------------------------------------------------: | :------: |
|  eph  |                   If there is, then the message will be visible only to the person who pressed the button                   |    No    |
| reply |                                  If there is, the message will be sent as a reply message.                                  |    No    |
|  usr  |                            The ID of the user who can use the button, if not, everyone can use it                           |    No    |
|  mbr  | The ID of the user whose achievements will be shown, if absent, the achievements of the user who used the button are shown. |    No    |
{% endtab %}

{% tab title="Rank" %}
ID: cmd{rank}eph reply

Arguments:

|  Name |                                                  Description                                                 | Required |
| :---: | :----------------------------------------------------------------------------------------------------------: | :------: |
|  eph  |            If there is, then the message will be visible only to the person who pressed the button           |    No    |
| reply |                           If there is, the message will be sent as a reply message.                          |    No    |
|  mbr  | ID of the user whose card will be shown, if it is missing, the card of the user who used the button is shown |    No    |
{% endtab %}

{% tab title="Rank-set" %}
ID: cmd{rank-set}eph reply

Arguments:

|  Name |                                       Description                                       | Required |
| :---: | :-------------------------------------------------------------------------------------: | :------: |
|  eph  | If there is, then the message will be visible only to the person who pressed the button |    No    |
| reply |                If there is, the message will be sent as a reply message.                |    No    |
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Say" %}
ID: cmd{say}channelId{ID}messageId{ID}permission{ID}eph reply

Arguments:

|    Name    |                                       Description                                       | Requried |
| :--------: | :-------------------------------------------------------------------------------------: | :------: |
|     eph    | If there is, then the message will be visible only to the person who pressed the button |    No    |
|    reply   |                If there is, the message will be sent as a reply message.                |    No    |
|   update   |                         If there is, the message will be edited                         |    No    |
|  channelId |                       ID of the channel to search for the message                       |    No    |
|  messageId |                                        Message ID                                       |    No    |
| permission |                                      Permission ID                                      |    No    |

{% hint style="info" %}
The channelId and messageId arguments are used together, you can't use one
{% endhint %}

{% hint style="info" %}
The channelId and messageId arguments are used to output a message from a specific channel. In this way, you can create a button that will output any message from any channel.
{% endhint %}

{% file src="../.gitbook/assets/Видео 17-06-2023 11_26_02.mp4" %}

{% hint style="info" %}
The message is output via the channelId and messageId arguments together with the buttons and files attached to this message.
{% endhint %}

{% hint style="info" %}
If you insert a link to a message into the say command form, the bot will output a completely copied message.
{% endhint %}

{% file src="../.gitbook/assets/Видео 17-06-2023 11_36_45.mp4" %}
{% endtab %}

{% tab title="Statistics" %}
ID: cmd{stats}eph reply

Arguments:

|  Name |                                                           Description                                                          | Required |
| :---: | :----------------------------------------------------------------------------------------------------------------------------: | :------: |
|  eph  |                     If there is, then the message will be visible only to the person who pressed the button                    |    No    |
| reply |                                    If there is, the message will be sent as a reply message.                                   |    No    |
|  usr  |                             The ID of the user who can use the button, if not, everyone can use it                             |    No    |
|  mbr  | The ID of the user whose statistics will be displayed, if absent, the statistics of the user who used the button are displayed |    No    |
{% endtab %}

{% tab title="Inventory roles" %}
ID: cmd{inventory-roles} eph reply

Arguments:

<table><thead><tr><th width="216" align="center">Name</th><th width="299.66666666666663" align="center">Description</th><th align="center">Required</th></tr></thead><tbody><tr><td align="center">eph</td><td align="center">If there is, then the message will be visible only to the person who pressed the button</td><td align="center">No</td></tr><tr><td align="center">reply</td><td align="center">If there is, the message will be sent as a reply message.</td><td align="center">No</td></tr><tr><td align="center">usr</td><td align="center">The ID of the user who can use the button, if not, everyone can use it</td><td align="center">No</td></tr><tr><td align="center">mbr</td><td align="center">The ID of the user whose inventory roles will be displayed, if missing, the inventory roles of the user who used the button is displayed.</td><td align="center">No</td></tr></tbody></table>
{% endtab %}

{% tab title="Create custom role" %}
ID: cmd{custom-role}
{% endtab %}
{% endtabs %}
