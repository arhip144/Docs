# Выдать предмет

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

{% content-ref url="../data-types/profile.md" %}
[profile.md](../data-types/profile.md)
{% endcontent-ref %}
