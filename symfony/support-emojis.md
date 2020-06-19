---
description: Make doctrine and MySQL support emojis
---

# Support emojis

Links:

{% embed url="https://avris.it/blog/emojis-in-doctrine" %}

{% embed url="https://mathiasbynens.be/notes/mysql-utf8mb4" %}

What you have to do is make MySQL and Doctrine support utf8mb4 charset.

It seems that it's not necessary to repair and optimize tables. For some reason at the end of the process the columns change their name, so you have to do a schema update to fix that.

