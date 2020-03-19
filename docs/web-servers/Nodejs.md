---
layout: default
title: Node.js 
parent: Web Servers
nav_order: 3
---

# Node.js Web Server
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


# Introduction
Node.js, first released in 2009, is a cross-platform runtime for running server-side JavaScript applications. Although it only shares a tiny portion of web servers market currently, there are many advantages that make Node.js one of the popular modern web development technologies. 

First, the benefit of using single language covering the full web development cycle from front-end development (client side) to back-end development (server side) does not only shorten the learning curve, but also simplifier the deployment. 

Second, Node.js uses single-threaded, non-blocking, asynchronous event-driven mechanism, which proved to be efficient in memory allocation as well as handling requests.

Moreover, Node.js is open sourced, and has a large and active community of developers who keep on continuously contributing towards its further development and improvement.

Although Node.js is not a part of LAMP stack, because of all the reasons mentioned above, we decide to include a basic installation guide to our user manual. 

# Installation
The first two steps are the same for all the installation guidance.

**Step 1.** Open a terminal, login to our AWS ubuntu instance.
![login](../../assets/images/login.png)

**Step 2.** (optional) Update the repositories and the ubuntu EC2 instance, if we haven't done it when we first login.
```bash
$ sudo apt update -y && sudo apt upgrade -y
```
![upadate](../../assets/images/update.png)

**Step 3.** Install *nvm* Node Version Manager.
```bash
$ wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```
The command downloads a script file and runs it to install *nvm*, which enables us to install multiple versions of node and switch between them. 
![nvm-install](../../assets/images/nvm-install.png)

**Step 4.** Active *nvm*
run the command below to active the nvm.
```bash
$ . ~/.nvm/nvm.sh
```
We can verify the installation by type the following command then.
```bash
$ command -v nvm
```
It shall print out nvm in the terminal. 

**Step 5.** Install the latest version of node using *nvm*.
```bash
$ nvm install node
```
The installation also has *npm*, Node Package Manager, installed, which can be used to install additional third party modules. 
![node-install](../../assets/images/node-install.png)

**Step 6.** Verify node installed successfully
```bash
$ node --version
```
The command prints out the node version installed.
![node-version](../../assets/images/node-version.png)

**Step 7.** (optional) Install AWS SDK for Javascript.
Node.js provides a collection of built-in modules, as well as huge amount of third party code that we can use to build application; however if we plan to integrate more AWS services into our application, we need to install AWS SDK for Javascript.

AWS SDK for Javascript is a JavaScript API Amazon provides for accessing AWS services. The image below shows the services that are available in the SDK.
![sdk](../../assets/images/sdk.png)

Install SDK for Node.js is the same as installing other modules using npm. Inside the project folder, run the following command in the terminal.
```bash
$ npm install aws-sdk
```
If we just created our project folder, make sure to type *npm init -y* first to initialize the project and create a package.json file.

![sdk-install](../../assets/images/sdk-install.png)

After finishing all the steps above, the environment is ready for coding Node.js application.

# Configuration / Example
not finished yet

```javascript
//app.js
const express = require("express"),
      app = express();
      
module.exports = (database) => {
    const dbQuery = require("./query")(database);
    app.use("/", dbQuery);
    return app;
};

//server.js
const database = require("../database/DB");
const app = require("./app")(database);
const port = process.env.PORT || 8080;

app.listen(port, () => {
	console.log(`\nServer running at ${port}`);
});

```