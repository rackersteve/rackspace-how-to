---
permalink: use-an-api-call-to-stop-a-cloud-server/
audit_date: '2020-07-17'
title: Use an API call to stop a cloud server
type: article
created_date: '2020-07-17'
created_by: Daniel Haile
last_modified_date: '2020-07-17'
last_modified_by: Cat Lookabaugh
product: Cloud Servers
product_url: cloud-servers
---

You might need to stop a cloud server for multiple reasons, including the following ones: 

- To test your disaster recovery procedures 
- To upgrade a server by creating a new server but leaving the old one in a stopped state
- To determine whether the server is still actively in use
- To assist with data recovery

You can use the Cloud Server Application Programmer Interface (API) by using a cURL&reg;
command, a script, or the interactive website application, Pitchfork.  To use Pitchfork
to stop a server, perform the following steps:

1. Log in to [Pithfork](https://pitchfork.rax.io/servers/#stop_server-cloud_servers/).
2. Scroll down to **Stop Server** in the **Server Actions** section.
3. Click **Details**.
4. Insert the instance UUID, which you can find in the Cloud Control Panel.
5. Click **Post**.

This command stops the server, and the server no longer accepts connections. 

**Note:** Rackspace continues to bill the owner of the server continues even if a server
is stopped. To stop getting billed, delete the server.

To reactivate a server in stopped state, contact Rackspace Support,
or send us a ticket with the re-activation request.
