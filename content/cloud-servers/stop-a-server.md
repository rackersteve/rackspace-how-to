---
permalink: stop-a-server/
audit_date: '2020-06-08'
title: Stop a cloud server via Api call
type: article
created_date: '2020-07-17'
created_by: Rackspace Support
last_modified_date: '2020-07-17'
last_modified_by: Daniel Haile
product: Cloud Servers
product_url: cloud-servers
---

A common use case for stopping a server is to determine whether the
server is still actively in use. Customer may need to stop a server 
for multiple reason like: test their disaster recovery procedure.
Or eventually, they need to upgrade a server by spinning a new
server and leave the old one in stop state, this can be helpful
in case od data recovery.The quickest and easiest way to stop a server. 
It's by using our customer api endpoint:

- Log in to the  API Interactive Website Application: 
  [Pithfork](https://pitchfork.rax.io/servers/#stop_server-cloud_servers/).
- Insert the instance UUID that can be found in the Cloud Control Panel

These commands stop the server, and the server no longer
accepts connections. Please be aware that your account will be
charged for using the disk space attached to your server. 


To reactivate a server in stop state, please contact rackspace support,
or send us a ticket with the re-activation request.
 
 