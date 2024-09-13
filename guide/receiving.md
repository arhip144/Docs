---
icon: plus-large
---

# Receiving currency, experience, reputations

To set up receiving currency/experience/reputation, you need to execute the /manager-settings command and select Receiving currency, experience, reputation in the drop-down menu

<figure><img src="../.gitbook/assets/изображение_2022-10-20_182438085.png" alt=""><figcaption></figcaption></figure>

Level factor: 10 (Each new level, the amount of experience to the next level increases by 10)

* ️For the message: \
  Awarded for a message in non-excluded text channels. Excluded channels can be configured in "Channels".
* For activity in voice channels: \
  Awarded for one minute of communication in non-excluded voice channels, with the microphone turned on and with at least one person.\
  :warning:Activity in voice channels is considered if there is more than one PERSON in the channel with the microphone turned on.\
  :warning:Activity with the microphone turned off does not count
* &#x20;For the invitation: \
  Awarded with one invitation to the server.\
  :warning:To correctly track the invitation, the bot must have the permission to "Manage the server". This permission is required to view the invitations and their changes.
* For bump: \
  Awarded for one server bump with the help of commands from other bots. For example: /bump, /up, /like
* For like: \
  Awarded for another user's like (/like). Awarded to both users (the one who sent the like, the one who received the like)
* For an item found for the first time: \
  Awarded for the item that the user found for the first time.

{% hint style="success" %}
When you change the "level factor" parameter, the bot will automatically change the user levels in accordance with the new level factor.
{% endhint %}
