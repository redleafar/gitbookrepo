---
description: >-
  Install mongoDB in a EC2 instance
  https://tecadmin.net/install-mongodb-on-centos/
---

# Install mongoDB in a EC2 instance

### Step 1 – Add MongoDB Yum Repository

```text
vi /etc/yum.repos.d/mongodb.repo
```

\(here I have some problems first I tried and got a 404 error and did not install, then I tried with the baseurl from here [https://dzone.com/articles/8-simple-steps-to-install-mongodb-with-authenticat-1](https://dzone.com/articles/8-simple-steps-to-install-mongodb-with-authenticat-1), that installed an old version, tried to uninstall it seems that didn't work, but tried again with the baseurl shown and it installed\)

```text
[MongoDB]
name=MongoDB Repository
baseurl=http://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/$basearch/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.2.asc
```

### 2. Install MongoDB Using the Below Command

```text
sudo yum install mongodb-org
```



