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
server is still actively in use. Customers may need to stop a server 
for multiple reason such as: test their disaster recovery procedure, 
upgrade a server by spinning a new server up and leaving the old one in stopped state. 
This can be helpful in case of data recovery. 

Use the API:

- Log in to the  API Interactive Website Application: 
  [Pithfork](https://pitchfork.rax.io/servers/#stop_server-cloud_servers/).
- Insert the instance UUID that can be found in the Cloud Control Panel

These commands stop the server, and the server no longer
accepts connections. The owner of the server will continue 
to be billed even if a server is stopped. To stop getting billed, 
delete the server

To reactivate a server in stop state, please contact rackspace support,
or send us a ticket with the re-activation request.
 
 
