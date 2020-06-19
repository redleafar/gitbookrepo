---
description: Make doctrine and MySQL support emojis
---

# Support emojis

Links:

{% embed url="https://avris.it/blog/emojis-in-doctrine" %}

{% embed url="https://mathiasbynens.be/notes/mysql-utf8mb4" %}

What you have to do is make MySQL and Doctrine support utf8mb4 charset.

For some reason at the end the columns change their name, so do a schema update to fix that.

