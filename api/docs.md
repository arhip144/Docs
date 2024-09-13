# Docs for API

{% hint style="info" %}
The base URL of the API: https://www.wetbot.space/api
{% endhint %}

## Getting an API key

The API key can be obtained in: /manager-settings -> API.

## Passing the API key in the request

To pass the API key in the request, use the Authorization header in headers, example:

{% code lineNumbers="true" %}
```javascript
{
   body: {
      //...Request body
   },
   headers: {
      Authorization: "Your API key"
   }
}
```
{% endcode %}

{% hint style="warning" %}
Any requests in headers must have a Content-Type header with the application/json value
{% endhint %}

## Rate limits

10 request per minute

## Response

{% tabs %}
{% tab title="Successful response" %}
{% code lineNumbers="true" %}
```javascript
{
    code: 2xx, //Number
    response: { //Object
        //response
    }
}
```
{% endcode %}
{% endtab %}

{% tab title="Response with an error" %}
{% code lineNumbers="true" %}
```javascript
{
    code: 4xx,  //Number
    message: "Error message"  //String
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Requests

{% tabs %}
{% tab title="Give item" %}
Type: POST\
Route: `/guilds/:guildId/users/:userId/inventory`\
Arguments: \
:guildId - server ID\
:userId - user ID\
Request body:

{% code lineNumbers="true" fullWidth="false" %}
```json
{
    "items": [ //Array
        { //First item
            "itemID": "id", //String
            "amount": 10 //Number -1000000000 - 1000000000
        },
        { //Second item
            "itemID": "id", //String
            "amount": 10 //Number -1000000000 - 1000000000
        }
    ]
}
```
{% endcode %}

The return value is the user profile object:

{% code overflow="wrap" %}
```javascript
{
    userID: //User ID (String)
    guildID: //Server ID (String)
    totalxp: //Total amount of experience (Number)
    seasonTotalXp: //Total amount of experience per season (Number)
    xp: //Number of experience (Number)
    seasonXp: //Number of seasonal experience (Number)
    xpSession: //Amount of experience per session (Number)
    rpSession: //Number of reputation per session (Number)
    level: //Level (Number)
    seasonLevel: //Seasonal level (Number)
    messages: //Number of messages (Number)
    hours: //Number of hours in voice channels (Number)
    rp: //Number of reputation (Number)
    hoursSession: //Number of hours per session (Number)
    likes: //Number of likes (Number)
    currency: //Amount of currency (Number)
    currencySession: //Amount of currency per session (Number)
    currencySpent: //Amount of currency spent(Number)
    stats: { //Statistics
        daily: { //Per day
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumpers (Number) giveawaysCreated: //Number of hands created (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of animal quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        },
        weekly: { //For the week
            totalxp: //Total amount of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumpers (Number)
            giveawaysCreated: //Number of created hands (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of completed quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        },
        monthly: { //Per month
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of hands created (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of quests requested (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the     market(Number)
        },
        yearly: { //For the year
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of created hands (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of requested quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        }
    },
    itemsSession: [ //Items per session (Array)
        {
        itemID: // Item ID (String)
        amount: //Quantity (Number)
        }
    ],
    invites: //Number of invitations (Number)
    startTime: //Date of the beginning of communication in the voice channel (Date)
    inviterInfo: { //Information about the invitee (Object)
    userID: //ID of the user who invited (String)
    items: [{ //Items received by this user for an invitation(Array)
        ItemId: // Item ID (String)
        amount: //Quantity (Number)
    }]
    },
    bio: //User Information (String)
    birthday_day: //Birthday (Number)
    birthday_month: //Month of birth (Number)
    birthday_year: //Year of birth (Number)
    image: //Link to profile banner (String)
    bumps: //Number of bumps (Number)
    giveawaysCreated: //The number of hands created (Number)
    multiplyXP: //Experience Booster Multiplier (Number)
    multiplyXPTime: //The end date of the experience booster (Date)
    multiplyCUR: //Currency Booster Multiplier (Number)
    multiplyCURTime: //The end date of the currency booster (Date)
    multiplyLuck: //Good Luck Booster Multiplier (Number)
    multiplyLuckTime: //The end date of the good luck booster (Date)
    multiplyRP: //Reputation Booster Multiplier (Number)
    multiplyRPTime: //The end date of the reputation booster (Date)
    daysStreak: //Series of Daily Awards (Number)
    lastDaily: //Date of taking the last daily reward (Date)
    lastLike: //Date of the last like (Date)
    fishing: //Number of fishing (Number)
    mining: //Number of mining (Number)
    maxDaily: //Maximum Day in Daily Rewards (Number)
    wormholeTouched: //Number of taken wormholes (Number)
    doneQuests: //Number of completed quests (Number)
    itemsSoldOnMarketPlace: //Number of items sold on the market (Number)
    inventory: [{ //Invert (Array)
        itemID: // Item ID (String)
        amount: //Number of
        fav: //In favorites (Boolean)
    }],
    achievments: [{ //Achievements (Array)
        achievmentID: //Achievement ID (String)
    }],
    roles: [], //Roles added with the help of objects (Array)
    quests: [{ //Quests (Array)
        questID: //Quest ID (String)
        targets: [{ //Goals (Array)
            TargetID: //Goal ID (String)
            reached: //Completed quantity (Number)
            finished: //Goal completed (Boolean)
        }],
        finished: //Quest completed (Boolean)
        finishedDate: //Date of completion of the quest (Date)
    }],
    blockActivities: { //Blocking activities (Object)
        message: { //Receiving for messages (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        voice: { //Receiving in one minute in the voice channel (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        invite: { //Receiving for an invitation (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        bump: { //Getting for bump (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        like: { //Getting XP for like (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        item: { //Getting for an item found in the first (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
        }
    },
    links: { //Links to social networks (Object)
        VK: //VKontakte (String)
        TikTok: //TikTok(String)
        Instagram: //Instagram (String)
        Steam: //Steam (String)
    },
    isHiden: //Profile hidden (Boolean)
    joinDateIsHiden: //The entry date is hidden (Boolean)
    achievmentsHiden: //Achievements are hidden (Boolean)
    sex: //Gender (String)
    hideSex: //Gender is hidden (Boolean)
    marry: //ID of the user with whom he is married (String)
    marryDate: //Date of marriage (Date)
    trophies: [], //Trophies (Array)
    trophyHide: //Trophies are hidden (Boolean)
    cs2premiere: {
        rank: //Rank in CS2 (Number)
        timeReset: //Date of rank reset (Date)
    },
    rank_card: { //Rank card (/rank) (Object)
        background: //Reference to background (String)
        background_brightness: //Background brightness (Number)
        background_blur: //Background blur (Number)
        font_color: { //Font color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_color: { //Experience scale color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_background_color: { //Background color of the experience scale (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        }
    },
    itemsOpened: //Number of open items (Number)
    wormholesSpawned: //Number of spawned wormholes (Number)
    itemsReceived: //Number of items received (Number)
    itemsCrafted: //Number of crafted items (Number)
    itemsUsed: //Number of items used (Number)
    itemsBoughtInShop: //Number of items purchased in the store (Number)
    itemsBoughtOnMarket: //The number of items purchased on the market (Number)
    itemsSold: //Number of items sold (Number)
    roleIncomeCooldowns: //Cooldowns of profitable roles (Map)
    dailyLimits: //Daily Limits (Object)
    weeklyLimits: //Weekly Limits (Object)
    monthlyLimits: //Monthly limits (Object)
    dropdownCooldowns: //Cooldowns of drop-down roles (Map)
    levelMention: //Mention when getting a level (Boolean)
     achievementMention: //Mention when receiving an achievement (Boolean)
    itemMention: //Mention upon receipt of the item (Boolean)
    roleincomention: //Mention of a Profitable role (Boolean) invitejoinment when rolling
    inviteJoinMention: //Mention when joining the server of the invitee (Boolean)
    inviteleavement: //Mention when exiting the invitee's server (Boolean)
    jobsCooldowns: //Cooldowns of work (Map)
    allJobsCooldown: //Cooldown of all work (Date)
    dropdownCooldowns: //Cooldowns of dropdown roles (Map)
    levelMention: //Mention when getting the (Boolean)
    achievementMention: //Mention when receiving an achievement (Boolean)
    itemMention: //Mention upon receipt of the item (Boolean)
    roleincomention: //Mention of a Profitable role (Boolean) invitejoinment when rolling
    inviteJoinMention: //Mention when joining the server of the invitee (Boolean)
    inviteleavement: //Mention when exiting the server of the invitee (Boolean)
    jobsCooldowns: //Cooldowns of work (Map)
    allJobsCooldown: //Cooldown of all work (Date)
    boosts: //Number of boosts of server (Number)
    works: //Number of works (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Give XP, RP, Currency" %}
Type: PATCH\
Route: `/guilds/:guildId/users/:userId`\
Arguments: \
:guildId - server ID\
:userId - user ID\
Request body:

```
{
    "currency": 100, //Curency (Number) -1000000000 - 1000000000
    "xp": 100, //Experience (Number) -100000 - 100000
    "rp": 100, //Reputation (Number) -100 - 100
}
```

The return value is the user profile object:

{% code overflow="wrap" %}
```javascript
{
    userID: //User ID (String)
    guildID: //Server ID (String)
    totalxp: //Total amount of experience (Number)
    seasonTotalXp: //Total amount of experience per season (Number)
    xp: //Number of experience (Number)
    seasonXp: //Number of seasonal experience (Number)
    xpSession: //Amount of experience per session (Number)
    rpSession: //Number of reputation per session (Number)
    level: //Level (Number)
    seasonLevel: //Seasonal level (Number)
    messages: //Number of messages (Number)
    hours: //Number of hours in voice channels (Number)
    rp: //Number of reputation (Number)
    hoursSession: //Number of hours per session (Number)
    likes: //Number of likes (Number)
    currency: //Amount of currency (Number)
    currencySession: //Amount of currency per session (Number)
    currencySpent: //Amount of currency spent(Number)
    stats: { //Statistics
        daily: { //Per day
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumpers (Number) giveawaysCreated: //Number of hands created (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of animal quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        },
        weekly: { //For the week
            totalxp: //Total amount of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumpers (Number)
            giveawaysCreated: //Number of created hands (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of completed quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        },
        monthly: { //Per month
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of hands created (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of quests requested (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the     market(Number)
        },
        yearly: { //For the year
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of created hands (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of requested quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        }
    },
    itemsSession: [ //Items per session (Array)
        {
        itemID: // Item ID (String)
        amount: //Quantity (Number)
        }
    ],
    invites: //Number of invitations (Number)
    startTime: //Date of the beginning of communication in the voice channel (Date)
    inviterInfo: { //Information about the invitee (Object)
    userID: //ID of the user who invited (String)
    items: [{ //Items received by this user for an invitation(Array)
        ItemId: // Item ID (String)
        amount: //Quantity (Number)
    }]
    },
    bio: //User Information (String)
    birthday_day: //Birthday (Number)
    birthday_month: //Month of birth (Number)
    birthday_year: //Year of birth (Number)
    image: //Link to profile banner (String)
    bumps: //Number of bumps (Number)
    giveawaysCreated: //The number of hands created (Number)
    multiplyXP: //Experience Booster Multiplier (Number)
    multiplyXPTime: //The end date of the experience booster (Date)
    multiplyCUR: //Currency Booster Multiplier (Number)
    multiplyCURTime: //The end date of the currency booster (Date)
    multiplyLuck: //Good Luck Booster Multiplier (Number)
    multiplyLuckTime: //The end date of the good luck booster (Date)
    multiplyRP: //Reputation Booster Multiplier (Number)
    multiplyRPTime: //The end date of the reputation booster (Date)
    daysStreak: //Series of Daily Awards (Number)
    lastDaily: //Date of taking the last daily reward (Date)
    lastLike: //Date of the last like (Date)
    fishing: //Number of fishing (Number)
    mining: //Number of mining (Number)
    maxDaily: //Maximum Day in Daily Rewards (Number)
    wormholeTouched: //Number of taken wormholes (Number)
    doneQuests: //Number of completed quests (Number)
    itemsSoldOnMarketPlace: //Number of items sold on the market (Number)
    inventory: [{ //Invert (Array)
        itemID: // Item ID (String)
        amount: //Number of
        fav: //In favorites (Boolean)
    }],
    achievments: [{ //Achievements (Array)
        achievmentID: //Achievement ID (String)
    }],
    roles: [], //Roles added with the help of objects (Array)
    quests: [{ //Quests (Array)
        questID: //Quest ID (String)
        targets: [{ //Goals (Array)
            TargetID: //Goal ID (String)
            reached: //Completed quantity (Number)
            finished: //Goal completed (Boolean)
        }],
        finished: //Quest completed (Boolean)
        finishedDate: //Date of completion of the quest (Date)
    }],
    blockActivities: { //Blocking activities (Object)
        message: { //Receiving for messages (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        voice: { //Receiving in one minute in the voice channel (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        invite: { //Receiving for an invitation (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        bump: { //Getting for bump (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        like: { //Getting XP for like (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        item: { //Getting for an item found in the first (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
        }
    },
    links: { //Links to social networks (Object)
        VK: //VKontakte (String)
        TikTok: //TikTok(String)
        Instagram: //Instagram (String)
        Steam: //Steam (String)
    },
    isHiden: //Profile hidden (Boolean)
    joinDateIsHiden: //The entry date is hidden (Boolean)
    achievmentsHiden: //Achievements are hidden (Boolean)
    sex: //Gender (String)
    hideSex: //Gender is hidden (Boolean)
    marry: //ID of the user with whom he is married (String)
    marryDate: //Date of marriage (Date)
    trophies: [], //Trophies (Array)
    trophyHide: //Trophies are hidden (Boolean)
    cs2premiere: {
        rank: //Rank in CS2 (Number)
        timeReset: //Date of rank reset (Date)
    },
    rank_card: { //Rank card (/rank) (Object)
        background: //Reference to background (String)
        background_brightness: //Background brightness (Number)
        background_blur: //Background blur (Number)
        font_color: { //Font color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_color: { //Experience scale color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_background_color: { //Background color of the experience scale (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        }
    },
    itemsOpened: //Number of open items (Number)
    wormholesSpawned: //Number of spawned wormholes (Number)
    itemsReceived: //Number of items received (Number)
    itemsCrafted: //Number of crafted items (Number)
    itemsUsed: //Number of items used (Number)
    itemsBoughtInShop: //Number of items purchased in the store (Number)
    itemsBoughtOnMarket: //The number of items purchased on the market (Number)
    itemsSold: //Number of items sold (Number)
    roleIncomeCooldowns: //Cooldowns of profitable roles (Map)
    dailyLimits: //Daily Limits (Object)
    weeklyLimits: //Weekly Limits (Object)
    monthlyLimits: //Monthly limits (Object)
    dropdownCooldowns: //Cooldowns of drop-down roles (Map)
    levelMention: //Mention when getting a level (Boolean)
     achievementMention: //Mention when receiving an achievement (Boolean)
    itemMention: //Mention upon receipt of the item (Boolean)
    roleincomention: //Mention of a Profitable role (Boolean) invitejoinment when rolling
    inviteJoinMention: //Mention when joining the server of the invitee (Boolean)
    inviteleavement: //Mention when exiting the invitee's server (Boolean)
    jobsCooldowns: //Cooldowns of work (Map)
    allJobsCooldown: //Cooldown of all work (Date)
    dropdownCooldowns: //Cooldowns of dropdown roles (Map)
    levelMention: //Mention when getting the (Boolean)
    achievementMention: //Mention when receiving an achievement (Boolean)
    itemMention: //Mention upon receipt of the item (Boolean)
    roleincomention: //Mention of a Profitable role (Boolean) invitejoinment when rolling
    inviteJoinMention: //Mention when joining the server of the invitee (Boolean)
    inviteleavement: //Mention when exiting the server of the invitee (Boolean)
    jobsCooldowns: //Cooldowns of work (Map)
    allJobsCooldown: //Cooldown of all work (Date)
    boosts: //Number of boosts of server (Number)
    works: //Number of works (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Get user" %}
Type: GET\
Route: `/guilds/:guildId/users/:userId`\
Arguments: \
:guildId - server ID\
:userId - user ID

The return value is the user profile object:

{% code overflow="wrap" %}
```javascript
{
    userID: //User ID (String)
    guildID: //Server ID (String)
    totalxp: //Total amount of experience (Number)
    seasonTotalXp: //Total amount of experience per season (Number)
    xp: //Number of experience (Number)
    seasonXp: //Number of seasonal experience (Number)
    xpSession: //Amount of experience per session (Number)
    rpSession: //Number of reputation per session (Number)
    level: //Level (Number)
    seasonLevel: //Seasonal level (Number)
    messages: //Number of messages (Number)
    hours: //Number of hours in voice channels (Number)
    rp: //Number of reputation (Number)
    hoursSession: //Number of hours per session (Number)
    likes: //Number of likes (Number)
    currency: //Amount of currency (Number)
    currencySession: //Amount of currency per session (Number)
    currencySpent: //Amount of currency spent(Number)
    stats: { //Statistics
        daily: { //Per day
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumpers (Number) giveawaysCreated: //Number of hands created (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of animal quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        },
        weekly: { //For the week
            totalxp: //Total amount of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumpers (Number)
            giveawaysCreated: //Number of created hands (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of completed quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        },
        monthly: { //Per month
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of hands created (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of quests requested (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the     market(Number)
        },
        yearly: { //For the year
            totalxp: //Total number of experience (Number)
            messages: //Number of messages (Number)
            hours: //Number of hours in voice channels (Number)
            rp: //Number of reputation (Number)
            likes: //Number of likes (Number)
            currency: //Number of currency (Number)
            invites: //Number of invitations (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of created hands (Number)
            wormholeTouched: //Number of wormholes (Number)
            doneQuests: //Number of requested quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        }
    },
    itemsSession: [ //Items per session (Array)
        {
        itemID: // Item ID (String)
        amount: //Quantity (Number)
        }
    ],
    invites: //Number of invitations (Number)
    startTime: //Date of the beginning of communication in the voice channel (Date)
    inviterInfo: { //Information about the invitee (Object)
    userID: //ID of the user who invited (String)
    items: [{ //Items received by this user for an invitation(Array)
        ItemId: // Item ID (String)
        amount: //Quantity (Number)
    }]
    },
    bio: //User Information (String)
    birthday_day: //Birthday (Number)
    birthday_month: //Month of birth (Number)
    birthday_year: //Year of birth (Number)
    image: //Link to profile banner (String)
    bumps: //Number of bumps (Number)
    giveawaysCreated: //The number of hands created (Number)
    multiplyXP: //Experience Booster Multiplier (Number)
    multiplyXPTime: //The end date of the experience booster (Date)
    multiplyCUR: //Currency Booster Multiplier (Number)
    multiplyCURTime: //The end date of the currency booster (Date)
    multiplyLuck: //Good Luck Booster Multiplier (Number)
    multiplyLuckTime: //The end date of the good luck booster (Date)
    multiplyRP: //Reputation Booster Multiplier (Number)
    multiplyRPTime: //The end date of the reputation booster (Date)
    daysStreak: //Series of Daily Awards (Number)
    lastDaily: //Date of taking the last daily reward (Date)
    lastLike: //Date of the last like (Date)
    fishing: //Number of fishing (Number)
    mining: //Number of mining (Number)
    maxDaily: //Maximum Day in Daily Rewards (Number)
    wormholeTouched: //Number of taken wormholes (Number)
    doneQuests: //Number of completed quests (Number)
    itemsSoldOnMarketPlace: //Number of items sold on the market (Number)
    inventory: [{ //Invert (Array)
        itemID: // Item ID (String)
        amount: //Number of
        fav: //In favorites (Boolean)
    }],
    achievments: [{ //Achievements (Array)
        achievmentID: //Achievement ID (String)
    }],
    roles: [], //Roles added with the help of objects (Array)
    quests: [{ //Quests (Array)
        questID: //Quest ID (String)
        targets: [{ //Goals (Array)
            TargetID: //Goal ID (String)
            reached: //Completed quantity (Number)
            finished: //Goal completed (Boolean)
        }],
        finished: //Quest completed (Boolean)
        finishedDate: //Date of completion of the quest (Date)
    }],
    blockActivities: { //Blocking activities (Object)
        message: { //Receiving for messages (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        voice: { //Receiving in one minute in the voice channel (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        invite: { //Receiving for an invitation (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        bump: { //Getting for bump (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        like: { //Getting XP for like (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        item: { //Getting for an item found in the first (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
        }
    },
    links: { //Links to social networks (Object)
        VK: //VKontakte (String)
        TikTok: //TikTok(String)
        Instagram: //Instagram (String)
        Steam: //Steam (String)
    },
    isHiden: //Profile hidden (Boolean)
    joinDateIsHiden: //The entry date is hidden (Boolean)
    achievmentsHiden: //Achievements are hidden (Boolean)
    sex: //Gender (String)
    hideSex: //Gender is hidden (Boolean)
    marry: //ID of the user with whom he is married (String)
    marryDate: //Date of marriage (Date)
    trophies: [], //Trophies (Array)
    trophyHide: //Trophies are hidden (Boolean)
    cs2premiere: {
        rank: //Rank in CS2 (Number)
        timeReset: //Date of rank reset (Date)
    },
    rank_card: { //Rank card (/rank) (Object)
        background: //Reference to background (String)
        background_brightness: //Background brightness (Number)
        background_blur: //Background blur (Number)
        font_color: { //Font color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_color: { //Experience scale color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_background_color: { //Background color of the experience scale (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        }
    },
    itemsOpened: //Number of open items (Number)
    wormholesSpawned: //Number of spawned wormholes (Number)
    itemsReceived: //Number of items received (Number)
    itemsCrafted: //Number of crafted items (Number)
    itemsUsed: //Number of items used (Number)
    itemsBoughtInShop: //Number of items purchased in the store (Number)
    itemsBoughtOnMarket: //The number of items purchased on the market (Number)
    itemsSold: //Number of items sold (Number)
    roleIncomeCooldowns: //Cooldowns of profitable roles (Map)
    dailyLimits: //Daily Limits (Object)
    weeklyLimits: //Weekly Limits (Object)
    monthlyLimits: //Monthly limits (Object)
    dropdownCooldowns: //Cooldowns of drop-down roles (Map)
    levelMention: //Mention when getting a level (Boolean)
     achievementMention: //Mention when receiving an achievement (Boolean)
    itemMention: //Mention upon receipt of the item (Boolean)
    roleincomention: //Mention of a Profitable role (Boolean) invitejoinment when rolling
    inviteJoinMention: //Mention when joining the server of the invitee (Boolean)
    inviteleavement: //Mention when exiting the invitee's server (Boolean)
    jobsCooldowns: //Cooldowns of work (Map)
    allJobsCooldown: //Cooldown of all work (Date)
    dropdownCooldowns: //Cooldowns of dropdown roles (Map)
    levelMention: //Mention when getting the (Boolean)
    achievementMention: //Mention when receiving an achievement (Boolean)
    itemMention: //Mention upon receipt of the item (Boolean)
    roleincomention: //Mention of a Profitable role (Boolean) invitejoinment when rolling
    inviteJoinMention: //Mention when joining the server of the invitee (Boolean)
    inviteleavement: //Mention when exiting the server of the invitee (Boolean)
    jobsCooldowns: //Cooldowns of work (Map)
    allJobsCooldown: //Cooldown of all work (Date)
    boosts: //Number of boosts of server (Number)
    works: //Number of works (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Spawn wormhole" %}
Type: POST\
Route: `/guilds/:guildId/wormholes/:wormholeId/spawn`\
Arguments: \
:guildId - server ID\
:wormholeId - wormhole ID

Return value wormhole object:

{% code overflow="wrap" %}
```javascript
{
    guildID: //Server ID (String)
    wormholeID: //Wormhole ID (String)
    chance: //Chance of spawning a wormhole (Number)
    ItemId: //Item ID (String)
    AmountFrom: //Minimum Quantity (Number)
    amountTo: //Maximum Quantity (Number)
    deleteTimeOut: //Wormhole Deletion Timeout (Number)
    deleteAfterTouch: //Wormhole is deleted (Boolean)
    enable: //Enabled (Boolean)
    styleId: //Style ID (String)
    webhookId: //Webhook ID (String)
    ThreadId: //Thread ID (String)
    permission: //Permission ID (String)
}
```
{% endcode %}
{% endtab %}

{% tab title="Get wormhole" %}
Type: GET\
Route: `/guilds/:guildId/wormholes/:wormholeId`\
Arguments: \
:guildId - server ID\
:wormholeId - wormhole ID

Return value wormhole object:

```javascript
{
    guildID: //Server ID (String)
    wormholeID: //Wormhole ID (String)
    chance: //Chance of spawning a wormhole (Number)
    ItemId: //Item ID (String)
    AmountFrom: //Minimum Quantity (Number)
    amountTo: //Maximum Quantity (Number)
    deleteTimeOut: //Wormhole Deletion Timeout (Number)
    deleteAfterTouch: //Wormhole is deleted (Boolean)
    enable: //Enabled (Boolean)
    styleId: //Style ID (String)
    webhookId: //Webhook ID (String)
    ThreadId: //Thread ID (String)
    permission: //Permission ID (String)
}
```
{% endtab %}
{% endtabs %}

