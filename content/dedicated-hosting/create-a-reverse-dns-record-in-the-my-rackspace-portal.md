---
permalink: create-a-reverse-dns-record-in-the-my-rackspace-portal/
audit_date:
title: 'Create a Reverse DNS Record in the My Rackspace Portal'
type: article
created_date: '2020-07-18'
created_by: Morgan Marion
last_modified_date:
last_modified_by:
product: dedicated-hosting
product_url: dedicated-hosted
---

# Create a Reverse DNS Record in the My Rackspace Portal

Reverse Domain Name Service (RDNS) records are also known as Pointer (PTR) records and they do the opposite to what an A record does. Typically, when you enter a domain name into your browser, the DNS system locates the IP address of the server hosting the domain. A Reverse DNS lookup does the opposite. It instead establishes what domain is associated with the IP address.

RDNS/PTR records are helpful for those running a mail server. Many recipient email servers check the sending IP address of the message, and if the Reverse DNS does not match the sending domain, they may they reject it, or mark it as spam. Having a Reverse DNS record for your domain may help prevent your messages from getting immediately rejected. However, all email systems have different approaches to spam prevention, so this should not be considered a guarantee.

Here are the steps for adding a Reverse DNS record in the MyRackspace.com Portal. This will map your server’s IP address to a domain name.

### Create a reverse DNS record

1. Log in to the MyRackspace.com Portal.

2. Navigate to Network > Domains (DNS) > Actions > PTR Records (Reverse DNS).

3. Find the device IP address you would like to edit and click on the pencil icon on the right.

4. Enter the domain information for the selected IP address and click "Save Changes"
