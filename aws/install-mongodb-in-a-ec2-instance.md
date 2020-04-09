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

\(here I had some problems. I tried and got a 404 error and it did not install, I tried checking the url in the browser and found the location [https://repo.mongodb.org/yum/redhat/8/mongodb-org/4.2/x86\_64/](https://repo.mongodb.org/yum/redhat/8/mongodb-org/4.2/x86_64/) and it worked\)

```text
[MongoDB]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/8/mongodb-org/4.2/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.2.asc
```

### 2. Install MongoDB Using the Below Command

```text
sudo yum install mongodb-org
```

### Step 3 – Start MongoDB Service

```text
sudo systemctl start mongod.service
```



