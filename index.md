---
layout: default
title: Home
nav_order: 1
description: "This Manual introduces the process on setting up a LAMP stack on Amazon Web Services (AWS)"
permalink: /
---

# AWS LAMP Stack Setup User Manual

---

## Introduction
Welcome to AWS LAMP stack setup user manual. This user manual is designed for new web developers who plan to develop or deploy their web applications on Amazon Web Services (AWS). 

As AWS provides huge amount of solutions for implementing various web stacks, the official documentation on AWS is overwhelming for beginners; therefore, we create this user manual dedicated mostly on LAMP stack. Although this manual has referred multiple sections from official documents of AWS as well as that of associated technologies, such as MongoDB and Nginx, we try to improve the understandability by adding more screenshots and explanation for the commands and codes used.

## Sections

### Launch an Ubuntu Instance
As you begin your foray into the realm of development you'll soon come to make use of Backend technologies for deploying services such as a Web Server or Database. The Web Server to host and serve your website and the Databse to store data for your Web Server to access and update.

Of course you could decide to run your Web Server and Databse on your local machine, but this method leads to issues down the line if you intend to make your website publicly accessible.

When you do eventually decide to show your work to the world, instead of hosting your website on your laptop, you can give your website to AWS for instant global hosting.

This section will guide you through all the necessary steps to Launch a Ubuntu Instance on AWS which we will use later to deploy our Web Server and Database in the following sections.


### Configure your Ubuntu Instance
Once you have launched a Ubuntu Instance you will need to do some light configuration to make your life easier.

This section will cover the configuration of the Elastic Block Storage (EBS) and Elastic IP services provided by AWS which will make using and scaling your Instance that much easier.


### Web servers
A Web server can be software or hardware, or both of them working together to host websites. It's one of the core components of web stack. In this manual, we introduce the installation and setup of three top open-source web servers. 
 
1. [Apache HTTP Server](/docs/web-servers/apache.md)

    Apache HTTP Server is one of the most popular open sourced web servers used in serving websites. It is written in C and XML, and was initially released on 1995. Its' large community contributes a variety of features, and many are implemented as external extensions or add-ons above the core functionalities. Our user manual covers two features besides the basic installation and configuration guidance.
<br>
1. [Nginx](/docs/web-servers/nginx.md)

    Nginx was first released in 2004, nine years later than Apache; however, it has surpassed Apache since 2016 and become the most widely used web server in the world. Besides being a web server, it can also be used as a reverse proxy, load balancer, mail proxy and HTTP cache, and load balancer is the most popular usage that can be found in modern web stack. 
<br>
3. [Node.js](docs/web-servers/Nodejs.md)

    Node.js, first released in 2009, is a cross-platform runtime for running server-side JavaScript applications. Although it only shares a tiny portion of web servers market currently, there are many advantages, such as single language on full stack development and high efficiency, make Node.js one of the popular modern web development technologies. 

### Databases
A Database is an organized collection of data that stored in a computer system. When talking about database in web development, we also refer it as the software that manages and manipulates the data, and interacts with end user. We include two databases setting guide: one supports the dominant relational database model - MySQL; another is the most popular NoSQL database - MongoDB.

1. [MySQL](/docs/databases/mysql.md) 

MySQL was first released in 1995, since then it has gradually become the most popular open source relational database. The latest release, 8.0 on April, 2018, introduced a great feature of Document Store, which enable us to store our JSON documents into collections and manage them using CRUD operations. 
<br>
1. [MongoDB](/docs/databases/mongodb.md) 

MongoDB, first released in 2009, is the most widely used NoSQL database. It is ranked first among document-oriented databases by DB-Engines. Being different from relational database using tables and restricted schema, MongoDB stores data objects as JSON-like documents inside a collection, thus it supports flexible data model that can accommodate data of any structure. 


### References
[Getting started with AWS EC2](https://aws.amazon.com/ec2/getting-started/)  
[Install MongoDB Community Edition](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)  
[Setting up Nginx and Nginx Plus as a web server and reverse proxy on AWS](https://www.nginx.com/blog/setting-up-nginx/)
