# API documentation

{% hint style="info" %}
API base URL: https://www.wetbot.space/api
{% endhint %}

## Getting an API key

You can get an API key at: [/manager-settings](../commands/admins.md) -> API.

## Passing the API key in a request

To pass the API key in a request, use the Authorization header in headers, for example:

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
In any request, the headers must include the Content-Type header with the value application/json
{% endhint %}

## Rate limits

You can send no more than 10 requests per minute.

## Responses

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

{% tab title="Error response" %}
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
{% tab title="Give an item" %}
Type: POST\
Path: `/guilds/:guildId/users/:userId/inventory`\
Parameters: \
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

Return value: the user profile object:

{% code overflow="wrap" %}
```javascript
{
    userID: //User ID (String)
    guildID: //Server ID  (String)
    totalxp: //Total experience (Number)
    seasonTotalXp: //Total season experience (Number)
    xp: //Experience amount (Number)
    seasonXp: //Season experience amount (Number)
    xpSession: //Experience amount for the session (Number)
    rpSession: //Reputation amount for the session (Number)
    level: //Level (Number)
    seasonLevel: //Season level (Number)
    messages: //Number of messages (Number)
    hours: //Hours in voice channels (Number)
    rp: //Reputation amount (Number)
    hoursSession: //Hours for the session (Number)
    likes: //Number of likes (Number)
    currency: //Currency amount (Number)
    currencySession: //Currency amount for the session (Number)
    currencySpent:  //Currency spent(Number)
    stats: {  //Statistics
        daily: { //Daily
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        weekly: { //Weekly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        monthly: { //Monthly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        yearly: { //Yearly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of giveaways created (Number)
            wormholeTouched: //Number of wormholes touched (Number)
            doneQuests: //Number of completed quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        }
    },
    itemsSession: [ //Items for the session (Array)
        {
            itemID: //Item ID (String)
            amount: //Amount (Number)
        }
    ],
    invites: //Number of invites (Number)
    startTime: //Date the voice channel session started (Date)
    inviterInfo: { //Information about the inviter (Object)
        userID: //ID of the user who invited (String)
        items: [{ //Items this user received for the invite(Array)
            itemID: //Item ID (String)
            amount: //Amount (Number)
        }]
    },
    bio: //User bio (String)
    birthday_day: //Birthday (day) (Number)
    birthday_month: //Birthday (month) (Number)
    birthday_year: //Birthday (year) (Number)
    image: //Profile banner link (String)
    bumps: //Number of bumps (Number)
    giveawaysCreated: //Number of giveaways created (Number)
    multiplyXP: //Experience booster multiplier (Number)
    multiplyXPTime: //Experience booster end date (Date)
    multiplyCUR: //Currency booster multiplier (Number)
    multiplyCURTime: //Currency booster end date (Date)
    multiplyLuck: //Luck booster multiplier (Number)
    multiplyLuckTime: //Luck booster end date (Date)
    multiplyRP: //Reputation booster multiplier (Number)
    multiplyRPTime: //Reputation booster end date (Date)
    daysStreak: //Daily reward streak (Number)
    lastDaily: //Date the last daily reward was claimed (Date)
    lastLike: //Date of the last like (Date)
    fishing: //Number of fishing attempts (Number)
    mining: //Number of mining attempts (Number)
    maxDaily: //Maximum day in daily rewards (Number)
    wormholeTouched: //Number of wormholes taken (Number)
    doneQuests: //Number of completed quests (Number)
    itemsSoldOnMarketPlace: //Number of items sold on the market (Number)
    inventory: [{ //Inventory (Array)
        itemID: //Item ID (String)
        amount: //Amount (Number)
        fav: //Favorited (Boolean)
    }],
    achievments: [{ //Achievements (Array)
        achievmentID: //Achievement ID (String)
    }],
    roles: [], //Roles added through items (Array)
    quests: [{ //Quests (Array)
        questID: //Quest ID (String)
        targets: [{ //Targets (Array)
            targetID: //Target ID (String)
            reached: //Completed amount (Number)
            finished: //Target completed (Boolean)
        }],
        finished: //Quest completed (Boolean)
        finishedDate: //Quest completion date (Date)
    }],
    blockActivities: { //Activity blocking (Object)
        message: { //Earning from messages (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        voice: { //Earning per minute in a voice channel (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        invite: { //Earning from invites (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        bump: { //Earning from bumps (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        like: { //Earning from likes (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        item: { //Earning from an item found for the first time (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
        }
    },
    links: { //Social network links (Object)
        VK: //VKontakte (String)
        TikTok: //TikTok(String)
        Instagram: //Instagram (String)
        Steam: //Steam (String)
    },
    isHiden: //Profile hidden (Boolean)
    joinDateIsHiden: //Join date hidden (Boolean)
    achievmentsHiden: //Achievements hidden (Boolean)
    sex: //Gender (String)
    hideSex: //Gender hidden (Boolean)
    marry: //ID of the user they are married to (String)
    marryDate: //Marriage date (Date)
    trophies: [], //Trophies (Array)
    trophyHide: //Trophies hidden (Boolean)
    cs2premiere: {
        rank: //CS2 rank (Number)
        timeReset: //Rank reset date (Date)
    },
    rank_card: { //Rank card (/rank) (Object)
        background: //Background link (String)
        background_brightness: //Background brightness (Number)
        background_blur: //Background blur (Number)
        font_color: //Font color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_color: { //Experience bar color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_background_color: { //Experience bar background color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        }
    },
    itemsOpened: //Number of items opened (Number)
    wormholesSpawned: //Number of wormholes spawned (Number)
    itemsReceived: //Number of items received (Number)
    itemsCrafted: //Number of items crafted (Number)
    itemsUsed: //Number of items used (Number)
    itemsBoughtInShop: //Number of items bought in the shop (Number)
    itemsBoughtOnMarket: //Number of items bought on the market (Number)
    itemsSold: //Number of items sold (Number)
    roleIncomeCooldowns: //Income role cooldowns (Map)
    dailyLimits: //Daily limits (Object)
    weeklyLimits: //Weekly limits (Object)
    monthlyLimits: //Monthly limits (Object)
    dropdownCooldowns: //Dropdown role cooldowns (Map)
    levelMention: //Mention when a level is gained (Boolean)
    achievementMention: //Mention when an achievement is received (Boolean)
    itemMention: //Mention when an item is received (Boolean)
    roleIncomeMention: //Mention when an income role cooldown ends (Boolean)
    inviteJoinMention: //Mention when an invited user joins the server (Boolean)
    inviteLeaveMention: //Mention when an invited user leaves the server (Boolean)
    jobsCooldowns: //Job cooldowns (Map)
    allJobsCooldown: //Cooldown for all jobs (Date)
    boosts: //Number of server boosts (Number)
    works: //Number of jobs worked (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Give XP, RP, currency" %}
Type: PATCH\
Path: `/guilds/:guildId/users/:userId`\
Parameters: \
:guildId - server ID\
:userId - user ID\
Request body:

```
{
    "currency": 100, //Currency (Number) -1000000000 - 1000000000
    "xp": 100, //Experience (Number) -100000 - 100000
    "rp": 100, //Reputation (Number) -100 - 100
}
```

Return value: the user profile object:

{% code overflow="wrap" %}
```javascript
{
    userID: //User ID (String)
    guildID: //Server ID  (String)
    totalxp: //Total experience (Number)
    seasonTotalXp: //Total season experience (Number)
    xp: //Experience amount (Number)
    seasonXp: //Season experience amount (Number)
    xpSession: //Experience amount for the session (Number)
    rpSession: //Reputation amount for the session (Number)
    level: //Level (Number)
    seasonLevel: //Season level (Number)
    messages: //Number of messages (Number)
    hours: //Hours in voice channels (Number)
    rp: //Reputation amount (Number)
    hoursSession: //Hours for the session (Number)
    likes: //Number of likes (Number)
    currency: //Currency amount (Number)
    currencySession: //Currency amount for the session (Number)
    currencySpent:  //Currency spent(Number)
    stats: {  //Statistics
        daily: { //Daily
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        weekly: { //Weekly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        monthly: { //Monthly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        yearly: { //Yearly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of giveaways created (Number)
            wormholeTouched: //Number of wormholes touched (Number)
            doneQuests: //Number of completed quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        }
    },
    itemsSession: [ //Items for the session (Array)
        {
            itemID: //Item ID (String)
            amount: //Amount (Number)
        }
    ],
    invites: //Number of invites (Number)
    startTime: //Date the voice channel session started (Date)
    inviterInfo: { //Information about the inviter (Object)
        userID: //ID of the user who invited (String)
        items: [{ //Items this user received for the invite(Array)
            itemID: //Item ID (String)
            amount: //Amount (Number)
        }]
    },
    bio: //User bio (String)
    birthday_day: //Birthday (day) (Number)
    birthday_month: //Birthday (month) (Number)
    birthday_year: //Birthday (year) (Number)
    image: //Profile banner link (String)
    bumps: //Number of bumps (Number)
    giveawaysCreated: //Number of giveaways created (Number)
    multiplyXP: //Experience booster multiplier (Number)
    multiplyXPTime: //Experience booster end date (Date)
    multiplyCUR: //Currency booster multiplier (Number)
    multiplyCURTime: //Currency booster end date (Date)
    multiplyLuck: //Luck booster multiplier (Number)
    multiplyLuckTime: //Luck booster end date (Date)
    multiplyRP: //Reputation booster multiplier (Number)
    multiplyRPTime: //Reputation booster end date (Date)
    daysStreak: //Daily reward streak (Number)
    lastDaily: //Date the last daily reward was claimed (Date)
    lastLike: //Date of the last like (Date)
    fishing: //Number of fishing attempts (Number)
    mining: //Number of mining attempts (Number)
    maxDaily: //Maximum day in daily rewards (Number)
    wormholeTouched: //Number of wormholes taken (Number)
    doneQuests: //Number of completed quests (Number)
    itemsSoldOnMarketPlace: //Number of items sold on the market (Number)
    inventory: [{ //Inventory (Array)
        itemID: //Item ID (String)
        amount: //Amount (Number)
        fav: //Favorited (Boolean)
    }],
    achievments: [{ //Achievements (Array)
        achievmentID: //Achievement ID (String)
    }],
    roles: [], //Roles added through items (Array)
    quests: [{ //Quests (Array)
        questID: //Quest ID (String)
        targets: [{ //Targets (Array)
            targetID: //Target ID (String)
            reached: //Completed amount (Number)
            finished: //Target completed (Boolean)
        }],
        finished: //Quest completed (Boolean)
        finishedDate: //Quest completion date (Date)
    }],
    blockActivities: { //Activity blocking (Object)
        message: { //Earning from messages (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        voice: { //Earning per minute in a voice channel (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        invite: { //Earning from invites (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        bump: { //Earning from bumps (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        like: { //Earning from likes (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        item: { //Earning from an item found for the first time (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
        }
    },
    links: { //Social network links (Object)
        VK: //VKontakte (String)
        TikTok: //TikTok(String)
        Instagram: //Instagram (String)
        Steam: //Steam (String)
    },
    isHiden: //Profile hidden (Boolean)
    joinDateIsHiden: //Join date hidden (Boolean)
    achievmentsHiden: //Achievements hidden (Boolean)
    sex: //Gender (String)
    hideSex: //Gender hidden (Boolean)
    marry: //ID of the user they are married to (String)
    marryDate: //Marriage date (Date)
    trophies: [], //Trophies (Array)
    trophyHide: //Trophies hidden (Boolean)
    cs2premiere: {
        rank: //CS2 rank (Number)
        timeReset: //Rank reset date (Date)
    },
    rank_card: { //Rank card (/rank) (Object)
        background: //Background link (String)
        background_brightness: //Background brightness (Number)
        background_blur: //Background blur (Number)
        font_color: //Font color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_color: { //Experience bar color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_background_color: { //Experience bar background color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        }
    },
    itemsOpened: //Number of items opened (Number)
    wormholesSpawned: //Number of wormholes spawned (Number)
    itemsReceived: //Number of items received (Number)
    itemsCrafted: //Number of items crafted (Number)
    itemsUsed: //Number of items used (Number)
    itemsBoughtInShop: //Number of items bought in the shop (Number)
    itemsBoughtOnMarket: //Number of items bought on the market (Number)
    itemsSold: //Number of items sold (Number)
    roleIncomeCooldowns: //Income role cooldowns (Map)
    dailyLimits: //Daily limits (Object)
    weeklyLimits: //Weekly limits (Object)
    monthlyLimits: //Monthly limits (Object)
    dropdownCooldowns: //Dropdown role cooldowns (Map)
    levelMention: //Mention when a level is gained (Boolean)
    achievementMention: //Mention when an achievement is received (Boolean)
    itemMention: //Mention when an item is received (Boolean)
    roleIncomeMention: //Mention when an income role cooldown ends (Boolean)
    inviteJoinMention: //Mention when an invited user joins the server (Boolean)
    inviteLeaveMention: //Mention when an invited user leaves the server (Boolean)
    jobsCooldowns: //Job cooldowns (Map)
    allJobsCooldown: //Cooldown for all jobs (Date)
    boosts: //Number of server boosts (Number)
    works: //Number of jobs worked (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Get a user" %}
Type: GET\
Path: `/guilds/:guildId/users/:userId`\
Parameters: \
:guildId - server ID\
:userId - user ID

Return value: the user profile object:

{% code overflow="wrap" %}
```javascript
{
    userID: //User ID (String)
    guildID: //Server ID  (String)
    totalxp: //Total experience (Number)
    seasonTotalXp: //Total season experience (Number)
    xp: //Experience amount (Number)
    seasonXp: //Season experience amount (Number)
    xpSession: //Experience amount for the session (Number)
    rpSession: //Reputation amount for the session (Number)
    level: //Level (Number)
    seasonLevel: //Season level (Number)
    messages: //Number of messages (Number)
    hours: //Hours in voice channels (Number)
    rp: //Reputation amount (Number)
    hoursSession: //Hours for the session (Number)
    likes: //Number of likes (Number)
    currency: //Currency amount (Number)
    currencySession: //Currency amount for the session (Number)
    currencySpent:  //Currency spent(Number)
    stats: {  //Statistics
        daily: { //Daily
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        weekly: { //Weekly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        monthly: { //Monthly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated:  //Number of giveaways created (Number)
            wormholeTouched:  //Number of wormholes touched (Number)
            doneQuests:  //Number of completed quests (Number)
            itemsSoldOnMarketPlace:  //Number of items sold on the market(Number)
        },
        yearly: { //Yearly
            totalxp: //Total experience (Number)
            messages: //Number of messages (Number)
            hours: //Hours in voice channels (Number)
            rp: //Reputation amount (Number)
            likes: //Number of likes (Number)
            currency: //Currency amount (Number)
            invites: //Number of invites (Number)
            bumps: //Number of bumps (Number)
            giveawaysCreated: //Number of giveaways created (Number)
            wormholeTouched: //Number of wormholes touched (Number)
            doneQuests: //Number of completed quests (Number)
            itemsSoldOnMarketPlace: //Number of items sold on the market(Number)
        }
    },
    itemsSession: [ //Items for the session (Array)
        {
            itemID: //Item ID (String)
            amount: //Amount (Number)
        }
    ],
    invites: //Number of invites (Number)
    startTime: //Date the voice channel session started (Date)
    inviterInfo: { //Information about the inviter (Object)
        userID: //ID of the user who invited (String)
        items: [{ //Items this user received for the invite(Array)
            itemID: //Item ID (String)
            amount: //Amount (Number)
        }]
    },
    bio: //User bio (String)
    birthday_day: //Birthday (day) (Number)
    birthday_month: //Birthday (month) (Number)
    birthday_year: //Birthday (year) (Number)
    image: //Profile banner link (String)
    bumps: //Number of bumps (Number)
    giveawaysCreated: //Number of giveaways created (Number)
    multiplyXP: //Experience booster multiplier (Number)
    multiplyXPTime: //Experience booster end date (Date)
    multiplyCUR: //Currency booster multiplier (Number)
    multiplyCURTime: //Currency booster end date (Date)
    multiplyLuck: //Luck booster multiplier (Number)
    multiplyLuckTime: //Luck booster end date (Date)
    multiplyRP: //Reputation booster multiplier (Number)
    multiplyRPTime: //Reputation booster end date (Date)
    daysStreak: //Daily reward streak (Number)
    lastDaily: //Date the last daily reward was claimed (Date)
    lastLike: //Date of the last like (Date)
    fishing: //Number of fishing attempts (Number)
    mining: //Number of mining attempts (Number)
    maxDaily: //Maximum day in daily rewards (Number)
    wormholeTouched: //Number of wormholes taken (Number)
    doneQuests: //Number of completed quests (Number)
    itemsSoldOnMarketPlace: //Number of items sold on the market (Number)
    inventory: [{ //Inventory (Array)
        itemID: //Item ID (String)
        amount: //Amount (Number)
        fav: //Favorited (Boolean)
    }],
    achievments: [{ //Achievements (Array)
        achievmentID: //Achievement ID (String)
    }],
    roles: [], //Roles added through items (Array)
    quests: [{ //Quests (Array)
        questID: //Quest ID (String)
        targets: [{ //Targets (Array)
            targetID: //Target ID (String)
            reached: //Completed amount (Number)
            finished: //Target completed (Boolean)
        }],
        finished: //Quest completed (Boolean)
        finishedDate: //Quest completion date (Date)
    }],
    blockActivities: { //Activity blocking (Object)
        message: { //Earning from messages (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        voice: { //Earning per minute in a voice channel (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        invite: { //Earning from invites (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        bump: { //Earning from bumps (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        like: { //Earning from likes (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
            RP: //Reputation (Boolean)
            items: //Items (Boolean)
        },
        item: { //Earning from an item found for the first time (Object)
            XP: //Experience (Boolean)
            CUR: //Currency (Boolean)
        }
    },
    links: { //Social network links (Object)
        VK: //VKontakte (String)
        TikTok: //TikTok(String)
        Instagram: //Instagram (String)
        Steam: //Steam (String)
    },
    isHiden: //Profile hidden (Boolean)
    joinDateIsHiden: //Join date hidden (Boolean)
    achievmentsHiden: //Achievements hidden (Boolean)
    sex: //Gender (String)
    hideSex: //Gender hidden (Boolean)
    marry: //ID of the user they are married to (String)
    marryDate: //Marriage date (Date)
    trophies: [], //Trophies (Array)
    trophyHide: //Trophies hidden (Boolean)
    cs2premiere: {
        rank: //CS2 rank (Number)
        timeReset: //Rank reset date (Date)
    },
    rank_card: { //Rank card (/rank) (Object)
        background: //Background link (String)
        background_brightness: //Background brightness (Number)
        background_blur: //Background blur (Number)
        font_color: //Font color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_color: { //Experience bar color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        },
        xp_background_color: { //Experience bar background color (Object)
            r: //Red channel (Number)
            g: //Green channel (Number)
            b: //Blue channel (Number)
            a: //Alpha channel (Number)
        }
    },
    itemsOpened: //Number of items opened (Number)
    wormholesSpawned: //Number of wormholes spawned (Number)
    itemsReceived: //Number of items received (Number)
    itemsCrafted: //Number of items crafted (Number)
    itemsUsed: //Number of items used (Number)
    itemsBoughtInShop: //Number of items bought in the shop (Number)
    itemsBoughtOnMarket: //Number of items bought on the market (Number)
    itemsSold: //Number of items sold (Number)
    roleIncomeCooldowns: //Income role cooldowns (Map)
    dailyLimits: //Daily limits (Object)
    weeklyLimits: //Weekly limits (Object)
    monthlyLimits: //Monthly limits (Object)
    dropdownCooldowns: //Dropdown role cooldowns (Map)
    levelMention: //Mention when a level is gained (Boolean)
    achievementMention: //Mention when an achievement is received (Boolean)
    itemMention: //Mention when an item is received (Boolean)
    roleIncomeMention: //Mention when an income role cooldown ends (Boolean)
    inviteJoinMention: //Mention when an invited user joins the server (Boolean)
    inviteLeaveMention: //Mention when an invited user leaves the server (Boolean)
    jobsCooldowns: //Job cooldowns (Map)
    allJobsCooldown: //Cooldown for all jobs (Date)
    boosts: //Number of server boosts (Number)
    works: //Number of jobs worked (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Spawn a wormhole" %}
Type: POST\
Path: `/guilds/:guildId/wormholes/:wormholeId/spawn`\
Parameters: \
:guildId - server ID\
:wormholeId - wormhole ID

Return value: the wormhole object:

{% code overflow="wrap" %}
```javascript
{
    guildID: //Server ID (String)
    wormholeID: //Wormhole ID (String)
    chance: //Wormhole spawn chance (Number)
    itemID: //Item ID (String)
    amountFrom: //Minimum amount (Number)
    amountTo: //Maximum amount (Number)
    deleteTimeOut: //Wormhole deletion timeout (Number)
    deleteAfterTouch: //Wormhole is deleted (Boolean)
    enable: //Enabled (Boolean)
    styleID: //Style ID (String)
    webhookId: //Webhook ID (String)
    threadId: //Thread ID (String)
    permission: //Permission ID (String)
}
```
{% endcode %}
{% endtab %}

{% tab title="Get a wormhole" %}
Type: GET\
Path: `/guilds/:guildId/wormholes/:wormholeId`\
Parameters: \
:guildId - server ID\
:wormholeId - wormhole ID

Return value: the wormhole object:

```javascript
{
    guildID: //Server ID (String)
    wormholeID: //Wormhole ID (String)
    chance: //Wormhole spawn chance (Number)
    itemID: //Item ID (String)
    amountFrom: //Minimum amount (Number)
    amountTo: //Maximum amount (Number)
    deleteTimeOut: //Wormhole deletion timeout (Number)
    deleteAfterTouch: //Wormhole is deleted (Boolean)
    enable: //Enabled (Boolean)
    styleID: //Style ID (String)
    webhookId: //Webhook ID (String)
    threadId: //Thread ID (String)
    permission: //Permission ID (String)
}
```
{% endtab %}
{% endtabs %}

