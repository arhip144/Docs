# Документация по API

{% hint style="info" %}
Базовый URL API: https://www.wetbot.space/api
{% endhint %}

## Получение API ключа

Ключ API можно получить в: [/manager-settings](../commands/admins.md) -> API.

## Передача API ключа в запросе

Для передачи API ключа в запросе используйте заголовок Authorization в headers, пример:

{% code lineNumbers="true" %}
```javascript
{
   body: {
      //...Тело запроса
   },
   headers: {
      Authorization: "Ваш API ключ"
   }
}
```
{% endcode %}

{% hint style="warning" %}
В любых запросах в headers должен присутствовать заголовок Content-Type со значением application/json
{% endhint %}

## Рейт лимиты

В одну минуту можно посылать не более 10 запросов.

## Ответы

{% tabs %}
{% tab title="Успешный ответ" %}
{% code lineNumbers="true" %}
```javascript
{
    code: 2xx, //Number
    response: { //Object
        //ответ
    }
}
```
{% endcode %}
{% endtab %}

{% tab title="Ответ с ошибкой" %}
{% code lineNumbers="true" %}
```javascript
{
    code: 4xx,  //Number
    message: "Сообщение ошибки"  //String
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Запросы

{% tabs %}
{% tab title="Выдать предмет" %}
Тип: POST\
Путь: `/guilds/:guildId/users/:userId/inventory`\
Параметры: \
:guildId - ID сервера\
:userId - ID пользователя\
Тело запроса:

{% code lineNumbers="true" fullWidth="false" %}
```json
{
    "items": [ //Array
        { //Первый предмет
            "itemID": "id", //String
            "amount": 10 //Number -1000000000 - 1000000000
        },
        { //Второй предмет
            "itemID": "id", //String
            "amount": 10 //Number -1000000000 - 1000000000
        }
    ]
}
```
{% endcode %}

Возвращаемое значение объект профиля пользователя:

{% code overflow="wrap" %}
```javascript
{
    userID: //ID пользователя (String)
    guildID: //ID сервера  (String)
    totalxp: //Общее количество опыта (Number)
    seasonTotalXp: //Общее количество опыта за сезон (Number)
    xp: //Количество опыта (Number)
    seasonXp: //Количество сезонного опыта (Number)
    xpSession: //Количество опыта за сессию (Number)
    rpSession: //Количество репутации за сессию (Number)
    level: //Уровень (Number)
    seasonLevel: //Сезонный уровень (Number)
    messages: //Количество сообщений (Number)
    hours: //Количество часов в голосовых каналах (Number)
    rp: //Количество репутации (Number)
    hoursSession: //Количество часов за сессию (Number)
    likes: //Количество лайков (Number)
    currency: //Количество валюты (Number)
    currencySession: //Количество валюты за сессию (Number)
    currencySpent:  //Количество потраченной валюты(Number)
    stats: {  //Статистика
        daily: { //За день
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        weekly: { //За неделю
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        monthly: { //За месяц
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        yearly: { //За год
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated: //Количество созданных раздач (Number)
            wormholeTouched: //Количество червоточин (Number)
            doneQuests: //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace: //Количество проданных предметов на маркете(Number)
        }
    },
    itemsSession: [ //Предметы за сессию (Array)
        {
            itemID: //ID предмета (String)
            amount: //Количество (Number)
        }
    ],
    invites: //Количество приглашений (Number)
    startTime: //Дата начала общения в голосовом канале (Date)
    inviterInfo: { //Информация о приглашателе (Object)
        userID: //ID пользователя который пригласил (String)
        items: [{ //Предметы полученые данным пользователем за приглашеие(Array)
            itemID: //ID предмета (String)
            amount: //Количество (Number)
        }]
    },
    bio: //Информация о пользователе (String)
    birthday_day: //День рождения (Number)
    birthday_month: //Месяц рождения (Number)
    birthday_year: //Год рождения (Number)
    image: //Ссылка на баннер профиля (String)
    bumps: //Количество бампов (Number)
    giveawaysCreated: //Количество созданных раздач (Number)
    multiplyXP: //Множитель бустера опыта (Number)
    multiplyXPTime: //Дата окончания бустера опыта (Date)
    multiplyCUR: //Множитель бустера валюты (Number)
    multiplyCURTime: //Дата окончания бустера валюты (Date)
    multiplyLuck: //Множитель бустера удачи (Number)
    multiplyLuckTime: //Дата окончания бустера удачи (Date)
    multiplyRP: //Множитель бустера репутации (Number)
    multiplyRPTime: //Дата окончания бустера репутации (Date)
    daysStreak: //Серия ежедневных наград (Number)
    lastDaily: //Дата взятия последней ежедневной награды (Date)
    lastLike: //Дата последнего лайка (Date)
    fishing: //Количество рыбалки (Number)
    mining: //Количество майнинга (Number)
    maxDaily: //Максимальный день в ежедневных наградах (Number)
    wormholeTouched: //Количество взятых червоточин (Number)
    doneQuests: //Количество завершенных квестов (Number)
    itemsSoldOnMarketPlace: //Количество предметов проданных на маркете (Number)
    inventory: [{ //Инвернтарь (Array)
        itemID: //ID предмета (String)
        amount: //Количество (Number)
        fav: //В избранном (Boolean)
    }],
    achievments: [{ //Достижения (Array)
        achievmentID: //ID достижения (String)
    }],
    roles: [], //Роли добавленные с помощтю предметов (Array)
    quests: [{ //Квесты (Array)
        questID: //ID квеста (String)
        targets: [{ //Цели (Array)
            targetID: //ID цели (String)
            reached: //Выполнено количество (Number)
            finished: //Цель завершена (Boolean)
        }],
        finished: //Квест завершен (Boolean)
        finishedDate: //Дата завершения квеста (Date)
    }],
    blockActivities: { //Блокировка активностей (Object)
        message: { //Получение за сообщения (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        voice: { //Получение за одну минуту в голосовом канале (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        invite: { //Получение за приглашение (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        bump: { //Получение за бамп (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        like: { //Получение за лайк (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        item: { //Получение за предмет найденный в первые (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
        }
    },
    links: { //Ссылки на социальные сети (Object)
        VK: //ВКонтакте (String)
        TikTok: //ТикТок(String)
        Instagram: //Инстаграм (String)
        Steam: //Стим (String)
    },
    isHiden: //Профиль скрыт (Boolean)
    joinDateIsHiden: //Дата вступления скрыта (Boolean)
    achievmentsHiden: //Достижения скрыты (Boolean)
    sex: //Пол (String)
    hideSex: //Пол скрыт (Boolean)
    marry: //ID пользователя, с кем состоит в браке (String)
    marryDate: //Дата брака (Date)
    trophies: [], //Трофеи (Array)
    trophyHide: //Трофеи скрыты (Boolean)
    cs2premiere: {
        rank: //Ранг в CS2 (Number)
        timeReset: //Дата сброса ранга (Date)
    },
    rank_card: { //Карточка ранга (/rank) (Object)
        background: //Ссылка на фон (String)
        background_brightness: //Яркость фона (Number)
        background_blur: //Размытие фона (Number)
        font_color: //Цвет шрифта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        },
        xp_color: { //Цвет шкалы опыта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        },
        xp_background_color: { //Цвет фона шкалы опыта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        }
    },
    itemsOpened: //Количество открытых предметов (Number)
    wormholesSpawned: //Количество заспавненных червоточин (Number)
    itemsReceived: //Количество полученных предметов (Number)
    itemsCrafted: //Количество скрафченных предметов (Number)
    itemsUsed: //Количество использованных предметов (Number)
    itemsBoughtInShop: //Количество купленных предметов в магазине (Number)
    itemsBoughtOnMarket: //Количество купленных предметов на маркете (Number)
    itemsSold: //Количество проданных предметов (Number)
    roleIncomeCooldowns: //Кулдауны доходных ролей (Map)
    dailyLimits: //Дневные  лимиты (Object)
    weeklyLimits: //Недельные  лимиты (Object)
    monthlyLimits: //Месячные  лимиты (Object)
    dropdownCooldowns: //Куладуны выпадающих ролей (Map)
    levelMention: //Упоминание при получении уровня (Boolean)
    achievementMention: //Упоминание при получении достижения (Boolean)
    itemMention: //Упоминание при получении предмета (Boolean)
    roleIncomeMention: //Упоминание при откате кулдауна доходной роли (Boolean)
    inviteJoinMention: //Упоминание при вступлении на сервер приглашенного (Boolean)
    inviteLeaveMention: //Упоминание при выходе с сервера приглашенного (Boolean)
    jobsCooldowns: //Кулдауны работы (Map)
    allJobsCooldown: //Кулдаун всей работы (Date)
    boosts: //Количество бустов сервера (Number)
    works: //Количество работ (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Выдать XP, RP, Валюту" %}
Тип: PATCH\
Путь: `/guilds/:guildId/users/:userId`\
Параметры: \
:guildId - ID сервера\
:userId - ID пользователя\
Тело запроса:

```
{
    "currency": 100, //Валюта (Number) -1000000000 - 1000000000
    "xp": 100, //Опыт (Number) -100000 - 100000
    "rp": 100, //Репутация (Number) -100 - 100
}
```

Возвращаемое значение объект профиля пользователя:

{% code overflow="wrap" %}
```javascript
{
    userID: //ID пользователя (String)
    guildID: //ID сервера  (String)
    totalxp: //Общее количество опыта (Number)
    seasonTotalXp: //Общее количество опыта за сезон (Number)
    xp: //Количество опыта (Number)
    seasonXp: //Количество сезонного опыта (Number)
    xpSession: //Количество опыта за сессию (Number)
    rpSession: //Количество репутации за сессию (Number)
    level: //Уровень (Number)
    seasonLevel: //Сезонный уровень (Number)
    messages: //Количество сообщений (Number)
    hours: //Количество часов в голосовых каналах (Number)
    rp: //Количество репутации (Number)
    hoursSession: //Количество часов за сессию (Number)
    likes: //Количество лайков (Number)
    currency: //Количество валюты (Number)
    currencySession: //Количество валюты за сессию (Number)
    currencySpent:  //Количество потраченной валюты(Number)
    stats: {  //Статистика
        daily: { //За день
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        weekly: { //За неделю
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        monthly: { //За месяц
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        yearly: { //За год
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated: //Количество созданных раздач (Number)
            wormholeTouched: //Количество червоточин (Number)
            doneQuests: //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace: //Количество проданных предметов на маркете(Number)
        }
    },
    itemsSession: [ //Предметы за сессию (Array)
        {
            itemID: //ID предмета (String)
            amount: //Количество (Number)
        }
    ],
    invites: //Количество приглашений (Number)
    startTime: //Дата начала общения в голосовом канале (Date)
    inviterInfo: { //Информация о приглашателе (Object)
        userID: //ID пользователя который пригласил (String)
        items: [{ //Предметы полученые данным пользователем за приглашеие(Array)
            itemID: //ID предмета (String)
            amount: //Количество (Number)
        }]
    },
    bio: //Информация о пользователе (String)
    birthday_day: //День рождения (Number)
    birthday_month: //Месяц рождения (Number)
    birthday_year: //Год рождения (Number)
    image: //Ссылка на баннер профиля (String)
    bumps: //Количество бампов (Number)
    giveawaysCreated: //Количество созданных раздач (Number)
    multiplyXP: //Множитель бустера опыта (Number)
    multiplyXPTime: //Дата окончания бустера опыта (Date)
    multiplyCUR: //Множитель бустера валюты (Number)
    multiplyCURTime: //Дата окончания бустера валюты (Date)
    multiplyLuck: //Множитель бустера удачи (Number)
    multiplyLuckTime: //Дата окончания бустера удачи (Date)
    multiplyRP: //Множитель бустера репутации (Number)
    multiplyRPTime: //Дата окончания бустера репутации (Date)
    daysStreak: //Серия ежедневных наград (Number)
    lastDaily: //Дата взятия последней ежедневной награды (Date)
    lastLike: //Дата последнего лайка (Date)
    fishing: //Количество рыбалки (Number)
    mining: //Количество майнинга (Number)
    maxDaily: //Максимальный день в ежедневных наградах (Number)
    wormholeTouched: //Количество взятых червоточин (Number)
    doneQuests: //Количество завершенных квестов (Number)
    itemsSoldOnMarketPlace: //Количество предметов проданных на маркете (Number)
    inventory: [{ //Инвернтарь (Array)
        itemID: //ID предмета (String)
        amount: //Количество (Number)
        fav: //В избранном (Boolean)
    }],
    achievments: [{ //Достижения (Array)
        achievmentID: //ID достижения (String)
    }],
    roles: [], //Роли добавленные с помощтю предметов (Array)
    quests: [{ //Квесты (Array)
        questID: //ID квеста (String)
        targets: [{ //Цели (Array)
            targetID: //ID цели (String)
            reached: //Выполнено количество (Number)
            finished: //Цель завершена (Boolean)
        }],
        finished: //Квест завершен (Boolean)
        finishedDate: //Дата завершения квеста (Date)
    }],
    blockActivities: { //Блокировка активностей (Object)
        message: { //Получение за сообщения (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        voice: { //Получение за одну минуту в голосовом канале (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        invite: { //Получение за приглашение (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        bump: { //Получение за бамп (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        like: { //Получение за лайк (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        item: { //Получение за предмет найденный в первые (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
        }
    },
    links: { //Ссылки на социальные сети (Object)
        VK: //ВКонтакте (String)
        TikTok: //ТикТок(String)
        Instagram: //Инстаграм (String)
        Steam: //Стим (String)
    },
    isHiden: //Профиль скрыт (Boolean)
    joinDateIsHiden: //Дата вступления скрыта (Boolean)
    achievmentsHiden: //Достижения скрыты (Boolean)
    sex: //Пол (String)
    hideSex: //Пол скрыт (Boolean)
    marry: //ID пользователя, с кем состоит в браке (String)
    marryDate: //Дата брака (Date)
    trophies: [], //Трофеи (Array)
    trophyHide: //Трофеи скрыты (Boolean)
    cs2premiere: {
        rank: //Ранг в CS2 (Number)
        timeReset: //Дата сброса ранга (Date)
    },
    rank_card: { //Карточка ранга (/rank) (Object)
        background: //Ссылка на фон (String)
        background_brightness: //Яркость фона (Number)
        background_blur: //Размытие фона (Number)
        font_color: //Цвет шрифта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        },
        xp_color: { //Цвет шкалы опыта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        },
        xp_background_color: { //Цвет фона шкалы опыта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        }
    },
    itemsOpened: //Количество открытых предметов (Number)
    wormholesSpawned: //Количество заспавненных червоточин (Number)
    itemsReceived: //Количество полученных предметов (Number)
    itemsCrafted: //Количество скрафченных предметов (Number)
    itemsUsed: //Количество использованных предметов (Number)
    itemsBoughtInShop: //Количество купленных предметов в магазине (Number)
    itemsBoughtOnMarket: //Количество купленных предметов на маркете (Number)
    itemsSold: //Количество проданных предметов (Number)
    roleIncomeCooldowns: //Кулдауны доходных ролей (Map)
    dailyLimits: //Дневные  лимиты (Object)
    weeklyLimits: //Недельные  лимиты (Object)
    monthlyLimits: //Месячные  лимиты (Object)
    dropdownCooldowns: //Куладуны выпадающих ролей (Map)
    levelMention: //Упоминание при получении уровня (Boolean)
    achievementMention: //Упоминание при получении достижения (Boolean)
    itemMention: //Упоминание при получении предмета (Boolean)
    roleIncomeMention: //Упоминание при откате кулдауна доходной роли (Boolean)
    inviteJoinMention: //Упоминание при вступлении на сервер приглашенного (Boolean)
    inviteLeaveMention: //Упоминание при выходе с сервера приглашенного (Boolean)
    jobsCooldowns: //Кулдауны работы (Map)
    allJobsCooldown: //Кулдаун всей работы (Date)
    boosts: //Количество бустов сервера (Number)
    works: //Количество работ (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Получить пользователя" %}
Тип: GET\
Путь: `/guilds/:guildId/users/:userId`\
Параметры: \
:guildId - ID сервера\
:userId - ID пользователя

Возвращаемое значение объект профиля пользователя:

{% code overflow="wrap" %}
```javascript
{
    userID: //ID пользователя (String)
    guildID: //ID сервера  (String)
    totalxp: //Общее количество опыта (Number)
    seasonTotalXp: //Общее количество опыта за сезон (Number)
    xp: //Количество опыта (Number)
    seasonXp: //Количество сезонного опыта (Number)
    xpSession: //Количество опыта за сессию (Number)
    rpSession: //Количество репутации за сессию (Number)
    level: //Уровень (Number)
    seasonLevel: //Сезонный уровень (Number)
    messages: //Количество сообщений (Number)
    hours: //Количество часов в голосовых каналах (Number)
    rp: //Количество репутации (Number)
    hoursSession: //Количество часов за сессию (Number)
    likes: //Количество лайков (Number)
    currency: //Количество валюты (Number)
    currencySession: //Количество валюты за сессию (Number)
    currencySpent:  //Количество потраченной валюты(Number)
    stats: {  //Статистика
        daily: { //За день
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        weekly: { //За неделю
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        monthly: { //За месяц
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated:  //Количество созданных раздач (Number)
            wormholeTouched:  //Количество червоточин (Number)
            doneQuests:  //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace:  //Количество проданных предметов на маркете(Number)
        },
        yearly: { //За год
            totalxp: //Общее количество опыта (Number)
            messages: //Количество сообщений (Number)
            hours: //Количество часов в голосовых каналах (Number)
            rp: //Количество репутации (Number)
            likes: //Количество лайков (Number)
            currency: //Количество валюты (Number)
            invites: //Количество приглашений (Number)
            bumps: //Количество бампов (Number)
            giveawaysCreated: //Количество созданных раздач (Number)
            wormholeTouched: //Количество червоточин (Number)
            doneQuests: //Количество звершенных квестов (Number)
            itemsSoldOnMarketPlace: //Количество проданных предметов на маркете(Number)
        }
    },
    itemsSession: [ //Предметы за сессию (Array)
        {
            itemID: //ID предмета (String)
            amount: //Количество (Number)
        }
    ],
    invites: //Количество приглашений (Number)
    startTime: //Дата начала общения в голосовом канале (Date)
    inviterInfo: { //Информация о приглашателе (Object)
        userID: //ID пользователя который пригласил (String)
        items: [{ //Предметы полученые данным пользователем за приглашеие(Array)
            itemID: //ID предмета (String)
            amount: //Количество (Number)
        }]
    },
    bio: //Информация о пользователе (String)
    birthday_day: //День рождения (Number)
    birthday_month: //Месяц рождения (Number)
    birthday_year: //Год рождения (Number)
    image: //Ссылка на баннер профиля (String)
    bumps: //Количество бампов (Number)
    giveawaysCreated: //Количество созданных раздач (Number)
    multiplyXP: //Множитель бустера опыта (Number)
    multiplyXPTime: //Дата окончания бустера опыта (Date)
    multiplyCUR: //Множитель бустера валюты (Number)
    multiplyCURTime: //Дата окончания бустера валюты (Date)
    multiplyLuck: //Множитель бустера удачи (Number)
    multiplyLuckTime: //Дата окончания бустера удачи (Date)
    multiplyRP: //Множитель бустера репутации (Number)
    multiplyRPTime: //Дата окончания бустера репутации (Date)
    daysStreak: //Серия ежедневных наград (Number)
    lastDaily: //Дата взятия последней ежедневной награды (Date)
    lastLike: //Дата последнего лайка (Date)
    fishing: //Количество рыбалки (Number)
    mining: //Количество майнинга (Number)
    maxDaily: //Максимальный день в ежедневных наградах (Number)
    wormholeTouched: //Количество взятых червоточин (Number)
    doneQuests: //Количество завершенных квестов (Number)
    itemsSoldOnMarketPlace: //Количество предметов проданных на маркете (Number)
    inventory: [{ //Инвернтарь (Array)
        itemID: //ID предмета (String)
        amount: //Количество (Number)
        fav: //В избранном (Boolean)
    }],
    achievments: [{ //Достижения (Array)
        achievmentID: //ID достижения (String)
    }],
    roles: [], //Роли добавленные с помощтю предметов (Array)
    quests: [{ //Квесты (Array)
        questID: //ID квеста (String)
        targets: [{ //Цели (Array)
            targetID: //ID цели (String)
            reached: //Выполнено количество (Number)
            finished: //Цель завершена (Boolean)
        }],
        finished: //Квест завершен (Boolean)
        finishedDate: //Дата завершения квеста (Date)
    }],
    blockActivities: { //Блокировка активностей (Object)
        message: { //Получение за сообщения (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        voice: { //Получение за одну минуту в голосовом канале (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        invite: { //Получение за приглашение (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        bump: { //Получение за бамп (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        like: { //Получение за лайк (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
            RP: //Репутация (Boolean)
            items: //Предметы (Boolean)
        },
        item: { //Получение за предмет найденный в первые (Object)
            XP: //Опыт (Boolean)
            CUR: //Валюта (Boolean)
        }
    },
    links: { //Ссылки на социальные сети (Object)
        VK: //ВКонтакте (String)
        TikTok: //ТикТок(String)
        Instagram: //Инстаграм (String)
        Steam: //Стим (String)
    },
    isHiden: //Профиль скрыт (Boolean)
    joinDateIsHiden: //Дата вступления скрыта (Boolean)
    achievmentsHiden: //Достижения скрыты (Boolean)
    sex: //Пол (String)
    hideSex: //Пол скрыт (Boolean)
    marry: //ID пользователя, с кем состоит в браке (String)
    marryDate: //Дата брака (Date)
    trophies: [], //Трофеи (Array)
    trophyHide: //Трофеи скрыты (Boolean)
    cs2premiere: {
        rank: //Ранг в CS2 (Number)
        timeReset: //Дата сброса ранга (Date)
    },
    rank_card: { //Карточка ранга (/rank) (Object)
        background: //Ссылка на фон (String)
        background_brightness: //Яркость фона (Number)
        background_blur: //Размытие фона (Number)
        font_color: //Цвет шрифта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        },
        xp_color: { //Цвет шкалы опыта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        },
        xp_background_color: { //Цвет фона шкалы опыта (Object)
            r: //Красный канал (Number)
            g: //Зеленый канал (Number)
            b: //Голубой канало (Number)
            a: //Альфа канал (Number)
        }
    },
    itemsOpened: //Количество открытых предметов (Number)
    wormholesSpawned: //Количество заспавненных червоточин (Number)
    itemsReceived: //Количество полученных предметов (Number)
    itemsCrafted: //Количество скрафченных предметов (Number)
    itemsUsed: //Количество использованных предметов (Number)
    itemsBoughtInShop: //Количество купленных предметов в магазине (Number)
    itemsBoughtOnMarket: //Количество купленных предметов на маркете (Number)
    itemsSold: //Количество проданных предметов (Number)
    roleIncomeCooldowns: //Кулдауны доходных ролей (Map)
    dailyLimits: //Дневные  лимиты (Object)
    weeklyLimits: //Недельные  лимиты (Object)
    monthlyLimits: //Месячные  лимиты (Object)
    dropdownCooldowns: //Куладуны выпадающих ролей (Map)
    levelMention: //Упоминание при получении уровня (Boolean)
    achievementMention: //Упоминание при получении достижения (Boolean)
    itemMention: //Упоминание при получении предмета (Boolean)
    roleIncomeMention: //Упоминание при откате кулдауна доходной роли (Boolean)
    inviteJoinMention: //Упоминание при вступлении на сервер приглашенного (Boolean)
    inviteLeaveMention: //Упоминание при выходе с сервера приглашенного (Boolean)
    jobsCooldowns: //Кулдауны работы (Map)
    allJobsCooldown: //Кулдаун всей работы (Date)
    boosts: //Количество бустов сервера (Number)
    works: //Количество работ (Number)
}
```
{% endcode %}
{% endtab %}

{% tab title="Заспавнить червоточину" %}
Тип: POST\
Путь: `/guilds/:guildId/wormholes/:wormholeId/spawn`\
Параметры: \
:guildId - ID сервера\
:wormholeId - ID червоточины

Возвращаемое значение объект червоточины:

{% code overflow="wrap" %}
```javascript
{
    guildID: //ID сервера (String)
    wormholeID: //ID червоточины (String)
    chance: //Шанс спавна червоточины (Number)
    itemID: //ID предмета (String)
    amountFrom: //Минимальное количестов (Number)
    amountTo: //Максимальное количество (Number)
    deleteTimeOut: //Таймаут удаления червоточины (Number)
    deleteAfterTouch: //Червоточина удаляется (Boolean)
    enable: //Включена (Boolean)
    styleID: //ID стиля (String)
    webhookId: //ID вебхука (String)
    threadId: //ID ветки (String)
    permission: //ID права (String)
}
```
{% endcode %}
{% endtab %}

{% tab title="Получить червоточину" %}
Тип: GET\
Путь: `/guilds/:guildId/wormholes/:wormholeId`\
Параметры: \
:guildId - ID сервера\
:wormholeId - ID червоточины

Возвращаемое значение объект червоточины:

```javascript
{
    guildID: //ID сервера (String)
    wormholeID: //ID червоточины (String)
    chance: //Шанс спавна червоточины (Number)
    itemID: //ID предмета (String)
    amountFrom: //Минимальное количестов (Number)
    amountTo: //Максимальное количество (Number)
    deleteTimeOut: //Таймаут удаления червоточины (Number)
    deleteAfterTouch: //Червоточина удаляется (Boolean)
    enable: //Включена (Boolean)
    styleID: //ID стиля (String)
    webhookId: //ID вебхука (String)
    threadId: //ID ветки (String)
    permission: //ID права (String)
}
```
{% endtab %}

{% tab title="Выдать достижение" %}
Тип: POST\
Путь: `/api/guilds/:guildId/users/:userId/achievements/:achievementId`\
Параметры: \
:guildId - ID сервера\
:userId - ID пользователя\
:achievementId - ID достижения

Возвращаемое значение объект достижения:

```javascript
{
    id: //String
    guildID: //String
    name: //String
    emoji: //String
    type: //Object || Number
    amount: //Number
    items: //Array
    roles: //Array
    rewards: [{
        type: //Number
        id: //String
        amount: //Number
    }],
    enable: //Boolean
    disabled_due_to_premium: //Boolean
}
```
{% endtab %}

{% tab title="Получить достижение" %}
Тип: GET\
Путь: `/api/guilds/:guildId/users/:userId/achievements/:achievementId`\
Параметры: \
:guildId - ID сервера\
:userId - ID пользователя\
:achievementId - ID достижения

Возвращаемое значение объект достижения:

```javascript
{
    id: //String
    guildID: //String
    name: //String
    emoji: //String
    type: //Object || Number
    amount: //Number
    items: //Array
    roles: //Array
    rewards: [{
        type: //Number
        id: //String
        amount: //Number
    }],
    enable: //Boolean
    disabled_due_to_premium: //Boolean
}
```
{% endtab %}

{% tab title="Забрать достижение у пользователя" %}
Тип: DELETE\
Путь: `/api/guilds/:guildId/achievements`\
Параметры: \
:guildId - ID сервера

Возвращаемое значение массив объектов достижений:

```javascript
[{
    id: //String
    guildID: //String
    name: //String
    emoji: //String
    type: //Object || Number
    amount: //Number
    items: //Array
    roles: //Array
    rewards: [{
        type: //Number
        id: //String
        amount: //Number
    }],
    enable: //Boolean
    disabled_due_to_premium: //Boolean
}]
```
{% endtab %}

{% tab title="Получить достижения сервера" %}
Тип: GET\
Путь: `/api/guilds/:guildId/users/:userId/achievements/:achievementId`\
Параметры: \
:guildId - ID сервера\
:userId - ID пользователя\
:achievementId - ID достижения

Возвращаемое значение объект достижения:

```javascript
{
    id: //String
    guildID: //String
    name: //String
    emoji: //String
    type: //Object || Number
    amount: //Number
    items: //Array
    roles: //Array
    rewards: [{
        type: //Number
        id: //String
        amount: //Number
    }],
    enable: //Boolean
    disabled_due_to_premium: //Boolean
}
```
{% endtab %}
{% endtabs %}

