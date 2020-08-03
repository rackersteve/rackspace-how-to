---
permalink: migrate-a-cloud-server-to-a-new-physical-host/
audit_date:
title: 'Migrate a Cloud Server to a new physical host
type: article
created_date: '2020-07-29'
created_by: Chris Silva
last_modified_date: '2020-07-29'
last_modified_by: Chris Silva
product: Cloud Servers
product_url: cloud-product
---

This article goes over the steps necessary to migrate a Cloud Server to a new physical host device. 


## Cloud Infrastructure

Your Cloud Server is a virtualized server that lives on a physical hypervisor. The hypervisor environment is managed by Rackspace but there are times in which a hypervisor can experience issues that impact your server performance. For this reason, Rackspace regularly migrates servers between hypervisor environments to ensure your server performs to the best of its ability. 


## Reasons to migrate

If you believe that your server performance is degraded, a server migration is a quick way to rule out any underlying infrastructure issues. Common reasons to migrate include:

- Unexplained degredation of performance
- Network connectivity
- High CPU/RAM usage
- High disk usage 

**Important**: While these can be an indication of a host level issue, the same issues could be on the server level and not be related to the host environment. A migration should not be considered a complete fix. 


## How to migrate your servers

The following steps describe how to reboot migrate a Cloud server to a new hypervisor in your Customer Portal.

**Note**: This process will not assign your server a new IP address. 

1. From your Customer Portal, select **Servers** and then click **Cloud Servers**. 

2. On the page that opens, select the server you want to migrate to open the Server Details page. 

3. On the Server Details page, select **Actions** and click **Migrate Server**. 

This will initiate the reboot migration process. The portal will show the status as **Resizing** but the server size will not change with this process. Your server will remain active for the majority of the process, but will require a reboot near the end of the migration. This process can take awhile depending on the amount of data on your server. Make sure you account for some downtime or perform this task outside of your normal business hours. 


## Next steps

Once the migration has completed, log into your server and verify the server is up and running and any processes not set to start on boot have been started. Please see this link for some things to check: <Ensure servers reboot successfully>(https://support.rackspace.com/how-to/ensure-servers-reboot-successfully/)


You can also verify the performance on your server to see if any improvements have been made as a result of the migration. In some rare instances, the new host environment could experience similar issues. You can migrate again as needed, but if multiple host environments are producing the same results, the issue is likely occurring at the server OS level. 
