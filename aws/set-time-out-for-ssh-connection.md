---
description: Set time out for ssh connection in order to avoid disconnection
---

# Set time out for ssh connection

You can set a keep alive option in your ~/.ssh/config file on your computer's home dir:

```text
ServerAliveInterval 50
```

Amazon AWS usually drops your connection after only 60 seconds of inactivity, so this option will ping the server every 50 seconds and keep you connected indefinitely.

