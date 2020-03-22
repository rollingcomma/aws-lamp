---
layout: default
title: Apache Trouble Shooting
nav_order: 1
parent: Trouble Shooting
---

# Apache Trouble Shooting
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Trouble shooting:
By default, Apache server will start automatically after installation.If the default page does not show after installation, we can further check from two aspects:
>1. Whether the Apache server is running.
>2. Does the security group of our instance have HTTP port 80 open.
  
**1.** Verify the Apache server is running.
By entering the below command in a terminal, we can get the service's status print out, as well as few latest lines from log file.
```bash
$ systemctl status apache2.service
```
![server](../../assets/images/server.png)
The screenshot above shows a normal running server. If it shows opposite, enter the command below to start the server.
```bash
$ sudo systemctl start apache2.service
```
We can also use *systemctl* command to stop or restart Apache server.
```bash
# To stop the server
$ sudo systemctl stop apache2.service
# To restart the server
$ sudo systemctl restart apache2.service
```

If the status shows the server is running, while we still can not get access to the default page, go to next step.

**2.** Check if the security group of our instance has the HTTP port 80 added in the inbound rules.
- Go to the AWS management console, 
![console](../../assets/images/console.png) 
</br>  
- Click EC2, 
![ec2](../../assets/images/instance.png)
</br> 
- then click running instances, select the instance,  
![](../../assets/images/running_instance.png)
</br> 
- in the description section, find the Security groups, 
![port enable](../../assets/images/security-groups1.png)
</br> 
- click view inbound rules to verify if the HTTP port 80 is in the list,
![view inbound](../../assets/images/security-groups2.png)
</br> 
- if not, click the security groups at the side bar under network & security section,
![security_group_m](../../assets/images/security_group_m.png)
</br> 
- find the security group that implied to our instance, launch-wizard-4 in the example,
![security_groups](../../assets/images/security_group.png) 
</br> 
- edit the inbound rules to add HTTP 80 port.
![port](../../assets/images/inbound.png)

Now try again in the browser to open the default page. If the below page shows, we can confirm that we have our Apache server setup.
![default](../../assets/images/default-page.png)