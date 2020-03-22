---
layout: default
title: Nginx Troubleshooting
parent: Troubleshooting
nav_order: 2
---

# Nginx Troubleshooting
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---
### Troubleshooting
If the server does not start properly, you can use below command to check the server status.

```bash
$ systemctl status nginx.service
```
![error](../../assets/images/fail-start-nginx.png)
This command will print out the service status, followed by first few log lines, which is very useful for targeting the problem when something goes wrong.  

In the screenshot above, the log message shows the service failed to start because default address:0.0.0.0:80 has already been in use, which could be caused by another web server, like Apache, listening to the same port. Enter following command to list the applications and the associated ports they are listening to.
```bash
$sudo lsof -i -P -n | grep LISTEN
```
![port](../../assets/images/port-used.png)
After you find out the application that occupies the address, Apache in this case, you have two options to resolve the problem:
1. stop the currently running service, and restart Nginx again. 
2. modify Nginx' configuration to bind to another port.
Here, you can stop Apache first to test if Nginx installed correctly. The configuration part in the manual will introduce the second solution.
![restart](../../assets/images/restart-nginx.png)
If no error message prints out, go back to the browser and refresh the page. you shall be able to see the following web page.
![default-page](../../assets/images/default-nginx.png)

