# Выдать XP, RP, Валюту

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

Возвращаемое значение: [Profile](../data-types/profile.md)
