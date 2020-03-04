# Introduction


# Installation
**Step 1.** open a terminal, login to our AWS ubuntu instance
[login]()

**Step 2.** (optional) update the repositories and the ubuntu EC2 instance, if we haven't done it when we first login.
```bash
$ sudo apt update -y && sudo apt upgrade -y
```
[upadate]()

**Step 3.** install MySQL server
```bash
$ sudo apt-get install mysql-server -y
```
[mysql]()
**Step 4** 
```bash
$ sudo mysql_secure_installation
```
Follow the instruction step by step to setup mysql sever
- set the VALIDATE PASSWORD plugin
  VALIDATE PASSWORD plugin is installed by default
    ```bash
    mysql> SET GLOBAL validate_password_length = 6;
    mysql> SET GLOBAL validate_password_number_count = 0;
    mysql> SET GLOBAL validate_password.policy = LOW;
    ```
- new password
- remove anonymous user
- disallow root login remotely
- remove test database and access it
- reload privilege table

**Step 5** verify the MySQL server is running
```bash
$ 
```
[mysql]()
# Configuration

```bash
$ cd /etc/mysql/mysql.conf.d
$ nano msqld.cnf
```
[config]()

```bash
$ scp -i <key.pem> filename <instance>:/folder
```
check the permission of the folder to allow your write