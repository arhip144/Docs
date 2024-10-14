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
