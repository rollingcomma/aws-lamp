# Launch an Ubuntu Instance on AWS EC2
Follow this guide to launch an Ubuntu instance on AWS EC2 🙌

## Introduction
First let's get some terminology out of the way:
* AWS -  Amazon Web Services
* EC2 - Elastic Compute Cloud (2)

AWS EC2 is a service provided by Amazon for deploying scalable computing resources in the cloud on globally distributed AWS servers.

AWS provides users the ability to deploy computing resources such as a web server, database, or containers globally with minimal ceremony and industry grade support and security from Amazon.

Without further ado, let's jump in.

---

## Launch an Ubuntu Instance
1. Go to [AWS](https://aws.amazon.com) and Create an account
![Create a Free Account on AWS](images/aws.png)
2. Open the [AWS Console](https://console.aws.amazon.com)
3. Open the EC2 Console by clicking "EC2" under the Compute section
4. Click "Running Instances"
5. Click "Launch Instance"
6. Select the Ubuntu Instacne (or whatever Linux distro you prefer)
7. Select "Configure Security Group" at the top
8. Select "Type" > "SSH" then select "Source" > "My IP"
9. Optionally enter a description for your machine
10. Click "Review and Launch" then "Launch"
11. You will be asked to "Select an existing key pair or create a new key pair", go ahead and choose your preferred option then Launch your instance


## Setup your machine to connect to your Instance
1. Open your ssh config file (`~/.ssh/config`)
2. Input the following and save the file:

``` ssh
Host ubuntu-aws
  User ubuntu
  HostName <public dns>
  IdentityFile <absolute path to key pair file>
  LocalForward <local port> localhost:<remote port>
```

* `Host` can be any name you want
* `User` should be the default user name for your distro found in AWS Docs
* `HostName` is the Public DNS of your Instance (found in the Description panel of your Instance)
* `IdentityFile` is the absolute path to the key pair file for your instance
* Optionally setup port forwarding with `LocalForward` to access remote ports on your local machine (ie. on your instance you have a server process serving on remote port `80` which you can map to port `8080` on your local machine with `LocalForward 8080 localhost:80`)
* Tip: you can forward multiple ports by adding another `LocalForward` line in your ssh config


## Connect to your Instance
1. Open your terminal
2. Enter the following command: `ssh ubuntu-aws`
3. Profit 🤑

---

## Next Steps
Now you have launched a Ubuntu Instance on AWS EC2, setup your machine to connect to your instance, and connected to your instance over ssh.

Next we will begin to go over how to setup a LAMP stack on your instance.
