---
icon: square-terminal
description: Schedules for wormholes, promocodes, and autogenerators
---

# Cron patterns

Used in [wormholes](wormholes.md), [promocodes](promocodes.md) (resetting uses), and [autogenerators](autogenerators.md).

## Cron pattern syntax

```
// ┌──────────────── (optional) seconds (0 - 59)
// │ ┌────────────── minutes (0 - 59)
// │ │ ┌──────────── hour (0 - 23)
// │ │ │ ┌────────── day of month (1 - 31)
// │ │ │ │ ┌──────── month (1 - 12, JAN-DEC)
// │ │ │ │ │ ┌────── day of week (0 - 6, SUN-Mon) 
// │ │ │ │ │ │       (0 to 6 are Sunday to Saturday; 7 is Sunday, the same as 0)
// │ │ │ │ │ │
// * * * * * *
```

## Quick examples

#### This runs every minute

\* \* \* \* \*

#### This runs every Sunday

0 0 0 \* \* 7

#### Every 30 minutes from 9 to 17 o'clock

0 \*/30 9-17 \* \* \*

#### Monday to Friday at 11:30

00 30 11 \* \* 1-5

#### Every 10 minutes

0 \*/10 \* \* \* \*

#### At midnight

00 00 00 \* \* \*

#### You can also use the following "nicknames" as a pattern.

| Nickname  | Description                                        |
| --------- | -------------------------------------------------- |
| @yearly   | Runs once a year, i.e. "0 0 1 1 \*".               |
| @annually | Runs once a year, i.e. "0 0 1 1 \*".               |
| @monthly  | Runs once a month, i.e. "0 0 1 \* \*".             |
| @weekly   | Runs once a week, i.e. "0 0 \* \* 0".              |
| @daily    | Runs once a day, i.e. "0 0 \* \* \*".              |
| @hourly   | Runs once an hour, i.e. "0 \* \* \* \*".           |

### [Handy site for generating cron patterns #1](https://www.freeformatter.com/cron-expression-generator-quartz.html)

### [Handy site for generating cron patterns #2](https://crontab.cronhub.io/)

### [Handy site for generating cron patterns #3](https://crontab.guru/)

### [Handy site for generating cron patterns #4](https://hexagon.github.io/cron-builder/)

{% hint style="info" %}
A cron pattern with an interval of less than 60 seconds cannot be created!
{% endhint %}

{% hint style="info" %}
All patterns run in the UTC time zone
{% endhint %}
