---
description: Представляет достижение WETBOT
---

# Achievement

<details>

<summary>Свойства</summary>

[id](achievement.md#id)

[guildID](achievement.md#guildid)

[name](achievement.md#name)

[emoji](achievement.md#emoji)

[type](achievement.md#type)

[amount](achievement.md#amount)

[items](achievement.md#items)

[roles](achievement.md#roles)

[rewards](achievement.md#rewards)

[enable](achievement.md#enable)

[disabled\_due\_to\_premium](achievement.md#disabled\_due\_to\_premium)

</details>

## Свойства

### [.id](achievement.md#id)

ID достижения\
Тип: [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)

***

### [.guildID](achievement.md#guildid)

ID сервера\
Тип: [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)

***

### [.name](achievement.md#name)

Название достижения\
Тип: [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)

***

### [.emoji](achievement.md#emoji)

Эмодзи достижения\
Тип: [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)

***

### [.type](achievement.md#type)

Тип достижения\
Тип: [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) | [AchievementType](achievement-type.md)

***

### [.amount](achievement.md#amount)

Количество для выполнения\
Тип: ?[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)

***

### [.items](achievement.md#items)

ID предметов для типа задач Item/Craft/FishingItem/MiningItem\
Тип: ?[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) <[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)>

***

### [.roles](achievement.md#roles)

ID ролей для типа задач Roles\
Тип: ?[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) <[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)>

***

### [.rewards](achievement.md#rewards)

Награды достижения\
Тип: [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) <[RewardData](reward-data.md)>

***

### [.enable](achievement.md#enable)

Достижение включено\
Тип: [Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean)

***

### [.disabled\_due\_to\_premium](achievement.md#disabled\_due\_to\_premium)

Выключено из-за отсутствующего премиума\
Тип: [Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean)
