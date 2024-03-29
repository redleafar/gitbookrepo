---
description: >-
  Connect django project to remote mongoDB database (using Djongo) allocated on
  EC2 aws instance
---

# Connect django project to remote mongoDB database (using Djongo)

## 1. Set up your user <a href="#id-1-set-up-your-user" id="id-1-set-up-your-user"></a>

First `ssh` into your server and enter the mongo shell by typing `mongo`. For this example, I will set up a user named `ian` and give that user read & write access to the `cool_db` database. **I had problems with single quotes use double instead as shown in the example**.

```bash
use cool_db

db.createUser(
{
    user: "test2",
    pwd: "cloud202001",
    roles: ["readWrite", "dbAdmin"]
});
```

## 2. Enable auth and open MongoDB access up to all IPs <a href="#id-2-enable-auth-and-open-mongodb-access-up-to-all-ips" id="id-2-enable-auth-and-open-mongodb-access-up-to-all-ips"></a>

Edit your MongoDB config file. On Ubuntu (It worked on Amazon Linux 2 AMI) **Warning:** do _not_ comment out the `bindIp` line without enabling authorization. Otherwise you will be opening up the whole internet to have full admin access to all mongo databases on your MongoDB server!:

`sudo vim /etc/mongod.conf`

Look for the `net` line and comment out the `bindIp` line under it, which is currently limiting MongoDB connections to _localhost_: **(I had to put 0.0.0.0 for the bind ip in order to avoid a connection refused error)**

```
# network interfaces
net:
  port: 27017
bindIp: 0.0.0.0  # Enter 0.0.0.0,:: to bind to all IPv4 and IPv6 addresses or, 
alternatively, use the net.bindIpAll setting
```

Scroll down to the `#security:` section and add the following line. Make sure to un-comment the `security:` line.

```
security:
  authorization: 'enabled'
```

## 3. Open port 27017 on your EC2 instance <a href="#id-3-open-port-27017-on-your-ec2-instance" id="id-3-open-port-27017-on-your-ec2-instance"></a>

* Go to your EC2 dashboard: [https://console.aws.amazon.com/ec2/](https://console.aws.amazon.com/ec2/)
* Go to `Instances` and scroll down to see your instance’s Security Groups. Eg, it will be something like `launch-wizard-4`
* Go to `Netword & Security` -> `Security Groups` -> `Inbound` tab -> `Edit` button.
* Make a new Custom TCP on port 27017, Source: Anywhere, 0.0.0.0/0

## 4. Last step: restart mongo daemon (mongod) <a href="#id-4-last-step-restart-mongo-daemon-mongod" id="id-4-last-step-restart-mongo-daemon-mongod"></a>

`sudo service mongod restart`

## 5. Set Database configuration on Django

```python
DATABASES = {
    'default': {
        'ENGINE': 'djongo',
        'NAME': 'contest',
        'CLIENT': {
            'host': '54.212.143.23',
            'port': 27017,
            'username': 'smartToolsGrupo8',
            'password': 'cloud202001'
        }
    }
}
```

I had problems trying to connect from a Heroku instance to an AWS mongoDB instance, so I tried with the Heroku mLab add-on and had to add two more parameters:

```python
DATABASES = {
    'default': {
        'ENGINE': 'djongo',
        'NAME': 'contest',
        'CLIENT': {
            'host': '54.212.143.23',
            'port': 27017,
            'username': 'smartToolsGrupo8',
            'password': 'cloud202001',
            'authSource': 'contest',
            'authMechanism': 'SCRAM-SHA-1'
        }
    }
}
```

It is possible that this works from the Heroku instance to the AWS mongoDB instance as well, but I have to try.

�
