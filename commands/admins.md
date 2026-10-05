---
icon: lock
---

# Admin commands

{% hint style="warning" %}
These commands are available to server administrators only.
{% endhint %}

| Command name | Description | Arguments |
| :---: | :---: | :---: |
| /achievement-give-to-user | **Give an achievement to a user** | <user> <achievement> |
| /achievement-take-from-user | **Take an achievement from a user** | <user> <achievement> |
| /backup | **Manage backups** | None |
| /components buttons add | **Add a button to a message** | <message _link_> <link\__or\_id_> \<Link \| Blue \| Red \| Grey \| Green><Row 1 \| Row 2 \| Row 3 \| Row 4 \| Row 5> <Column 1 \| Column 2 \| Column 3 \| Column 4 \| Column 5> \[name] \[emoji] \[disabled] |
| /components buttons remove | **Remove a button from a message** | <message _link_> <Row 1 \| Row 2 \| Row 3 \| Row 4 \| Row 5> <Column 1 \| Column 2 \| Column 3 \| Column 4 \| Column 5> |
| /cooldowns view | **View all cooldowns** | None |
| /cooldowns edit | **Change a cooldown** | <command\_name> <cooldown> |
| /cooldowns immune\_roles add | **Add an immune role** | <role> |
| /cooldowns immune\_roles delete | **Remove an immune role** | <role> |
| /cooldowns immune\_roles delete all | **Remove all immune roles** | None |
| /config fishing list | **List all fishing items** | None |
| /config fishing add-edit | **Add or edit a fishing item** | <item> <chance> <min\_amount> <max\_amount> <min\_xp> <max\_xp> |
| /config fishing delete-all | **Remove all fishing items** | None |
| /config voice-items list | **List all items for voice activity** | None |
| /config voice-items add-edit | **Add or edit an item for voice activity** | <item> <chance> <min\_amount> <max\_amount> |
| /config voice-items delete-all | **Remove all items from voice activity** | None |
| /config messages-items list | **List all items for text activity** | None |
| /config messages-items add-edit | **Add or edit an item for text activity** | <item> <chance> <min\_amount> <max\_amount> |
| /config messages-items delete-all | **Remove all items from text activity** | None |
| /dropdown-roles | **Create a dropdown list of roles to pick from** | <role1> \[role2] \[role3] \[role4] \[role5] \[role6] \[role7] \[role8] \[role9] \[role10] \[role11] \[role12] \[role13] \[role14] \[role15] \[role16] \[role17] \[role18] \[role19] \[role20] \[role21] \[role22] \[role23] \[role24] \[role25] |
| /embed-generator | **Embed generator** | None |
| /give-item member | **Give an item to a member** | <user> <item> \[amount] \[user2] \[user3] \[user4] \[user5] \[user6] \[user7] \[user8] \[user9] \[user10] |
| /give-item role | **Give an item to a role** | <role> <item> \[amount] \[role2] \[role3] \[role4] \[role5] \[role6] \[role7] \[role8] \[role9] \[role10] |
| /give level | **Give levels to a user** | <user> <amount> |
| /give experience | **Give experience to a user** | <user> <amount> |
| /give currency | **Give currency to a user** | <user> <amount> |
| /give reputation | **Give reputation to a user** | <user> <amount> |
| /give likes | **Give likes to a user** | <user> <amount> |
| /give role | **Give a role to /inventory-roles** | <user> <role> <amount> |
| /give season\_level | **Give season levels** | <user> <amount> |
| /manager-achievements | **Manage server achievements** | None |
| /manager-categories | **Manage shop categories** | None |
| /manager-channels | **Configure channel bonuses** | \[channel] |
| ⭐/manager-gifts | **Manage server gifts** | None |
| /manager-items | **Manage server items** | None |
| /manager-quests | **Manage server quests** | None |
| /manager-settings | **Manage server settings** | None |
| /manager-styles | **Manage server wormhole styles** | None |
| /manager-wormholes | **Manage server wormholes** | None |
| /manager-permissions | **Manage server permissions** | None |
| /manager-jobs | **Manage jobs** | None |
| /manager-promocodes | **Manage promocodes** | None |
| /promocode-autogenerators | **Manage promocode autogenerators** | None |
| /premium | **Buy premium and premium features** | None |
| /quest-give-to-user | **Give a quest to a user** | <user> <quest> |
| /quest-take-from-user | **Take a quest from a user** | <user> <quest> |
| /reset-limits daily | **Reset daily limits** | <user> <item> |
| /reset-limits weekly | **Reset weekly limits** | <user> <item> |
| /reset-limits monthly | **Reset monthly limits** | <user> <item> |
| /role-properties | **Configure role properties** | <role> |
| /say | **Send a message as WETBOT** | None |
| /set level | **Set a user's level** | <user> <amount> |
| /set experience | **Set a user's experience** | <user> <amount> |
| /set currency | **Set a user's currency** | <user> <amount> |
| /set reputation | **Set a user's reputation** | <user> <amount> |
| /set likes | **Set a user's likes** | <user> <amount> |
| /set season\_level | Set a user's season level | <user> <amount> |
| /set luck\_boost | **Set a luck boost** | <user> <percent> <time> |
| /set xp\_boost | **Set an experience boost** | <user> <percent> <time> |
| /set currency\_boost | **Set a currency boost** | <user> <percent> <time> |
| /set rp\_boost | **Set a reputation boost** | <user> <percent> <time> |
| /shop-add-edit | **Add or edit an item in the shop** | <item> <price> \[price\_type] \[amount] \[discount] |
| /shop-decrease-amount | **Decrease the amount of an item in the shop** | <item> <amount> |
| /shop-del | **Remove an item from the shop** | <item> |
| /shop-increase-amount | **Increase the amount of an item in the shop** | <item> <amount> |
| /take-item from-member | **Take an item from a member** | <user> <item> \[amount] \[user2] \[user3] \[user4] \[user5] \[user6] \[user7] \[user8] \[user9] \[user10] |
| /take-item from-role | **Take an item from a role** | <role> <item> \[amount] \[role2] \[role3] \[role4] \[role5] \[role6] \[role7] \[role8] \[role9] \[role10] |
| /take level | **Take levels from a user** | <user> <amount> |
| /take experience | **Take experience from a user** | <user> <amount> |
| /take currency | **Take currency from a user** | <user> <amount> |
| /take reputation | **Take reputation from a user** | <user> <amount> |
| /take likes | **Take likes from a user** | <user> <amount> |
| /take season\_level | **Take season levels from a user** | <user> <amount> |
| /take role | **Remove a role from /inventory-roles** | <user> <role> <amount> |
| /trophy give | **Give a trophy to a user** | \[user] \[trophy] |
| /trophy take | **Take a trophy from a user** | \[user] \[trophy] |
| /user-activities | **Enable or disable a user's ability to earn currency, experience, reputation, and items from activities** | <user> |
| /wipe | **Clear users with the specified parameters** | None |
| /wormhole-spawn | **Spawn a wormhole** | <wormhole> |

{% hint style="info" %}
< > - required argument \[ ] - optional argument | - OR If you can't see the commands, update your Discord client to the latest version.
{% endhint %}
