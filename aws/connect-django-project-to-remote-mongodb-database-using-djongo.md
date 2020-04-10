---
description: >-
  Connect django project to remote mongoDB database (using Djongo) allocated on
  EC2 aws instance
---

# Connect django project to remote mongoDB database \(using Djongo\)

## 1. Set up your user <a id="1-set-up-your-user"></a>

First `ssh` into your server and enter the mongo shell by typing `mongo`. For this example, I will set up a user named `ian` and give that user read & write access to the `cool_db` database.

```text
use cool_db

db.createUser({
    user: 'ian',
    pwd: 'secretPassword',
    roles: [{ role: 'readWrite', db:'cool_db'}]
})
```

## 2. Enable auth and open MongoDB access up to all IPs <a id="2-enable-auth-and-open-mongodb-access-up-to-all-ips"></a>

Edit your MongoDB config file. On Ubuntu \(It worked on Amazon Linux 2 AMI\) **Warning:** do _not_ comment out the `bindIp` line without enabling authorization. Otherwise you will be opening up the whole internet to have full admin access to all mongo databases on your MongoDB server!:

`sudo vim /etc/mongod.conf`

Look for the `net` line and comment out the `bindIp` line under it, which is currently limiting MongoDB connections to _localhost_:

```text
# network interfaces
net:
  port: 27017
#  bindIp: 127.0.0.1  <- comment out this line
```

Scroll down to the `#security:` section and add the following line. Make sure to un-comment the `security:` line.

```text
security:
  authorization: 'enabled'
```

## 3. Open port 27017 on your EC2 instance <a id="3-open-port-27017-on-your-ec2-instance"></a>

* Go to your EC2 dashboard: [https://console.aws.amazon.com/ec2/](https://console.aws.amazon.com/ec2/)
* Go to `Instances` and scroll down to see your instance’s Security Groups. Eg, it will be something like `launch-wizard-4`
* Go to `Netword & Security` -&gt; `Security Groups` -&gt; `Inbound` tab -&gt; `Edit` button.
* Make a new Custom TCP on port 27017, Source: Anywhere, 0.0.0.0/0

## 4. Last step: restart mongo daemon \(mongod\) <a id="4-last-step-restart-mongo-daemon-mongod"></a>

`sudo service mongod restart`

## 5.



