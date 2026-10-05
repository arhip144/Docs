---
description: Для создания кастомных ролей требуется премиум
icon: masks-theater
---

# Создание кастомной роли

## Что это?

Участники создают свои Discord-роли (цвет, название) командой `/custom-role`. Роль попадает в [инвентарь ролей](inventory-roles.md).

{% hint style="warning" %}
Требуется [премиум](../premium.md).
{% endhint %}

## Discord: первичная настройка

Введите [/manager-settings](../commands/admins.md) → раздел **Кастомные роли**.

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

| Параметр                        | Описание                                                     |
| ------------------------------- | ------------------------------------------------------------ |
| Позиция / создание под ролью    | Без опорной роли `/custom-role` недоступна                   |
| Канал модерации                 | Если задан — заявки на модерацию; иначе роль создаётся сразу |
| Право на кастомные роли         | Пресет [прав](permissions.md)                                |
| Отображать отдельно / временные | Hoist и timed-роли                                           |
| Минимум минут / лимит создания  | Ограничения                                                  |

Если есть канал модерации, заявки рассматривает персонал. Без канала роли выдаются в инвентарь автоматически.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

Команда игрока: [/custom-role](../commands/general.md).

Создание можно вынести [в кнопку](buttons.md#sozdanie-kastomnoi-roli).

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

## На сайте

{% content-ref url="../website/settings/custom-boosters.md" %}
[custom-boosters.md](../website/settings/custom-boosters.md)
{% endcontent-ref %}
