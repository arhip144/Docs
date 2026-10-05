---
description: Guide to creating a job
icon: briefcase-blank
---

# Creating a job

## What is this?

Jobs are actions for the `/work` command: the player picks a job and an action, and gets a success or a failure with rewards and cooldowns.

{% hint style="warning" %}
The `/work` command is available with [premium](../premium.md).
{% endhint %}

## Discord

Command [/manager-jobs](../commands/admins.md):

| Argument | Description |
| --- | --- |
| create | Create a new job |
| edit | Edit an existing one |
| copy | Copy |
| delete | Delete |
| view | List of all jobs |

### What can be configured

- Name, emoji, description, enabled/hidden
- Two actions (name + permission)
- For success and failure: chance, messages, images, cooldowns, rewards (currency/XP/RP/item)

Variables in messages: [Variables: jobs](../variables/jobs.md).

Players use [/work](../commands/general.md).

## On the website

Full list of fields:

{% content-ref url="../website/jobs.md" %}
[jobs.md](../website/jobs.md)
{% endcontent-ref %}
