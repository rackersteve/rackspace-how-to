---
permalink: installing-apache-on-centos-8/
audit_date:
title: 'Installing Apache on CentOS 8'
type: article
created_date: '2020-07-22'
created_by: Rackspace Support
last_modified_date:
last_modified_by:
product: Cloud Product
product_url: cloud-product
---

The Apache HTTP Server, colloquially called Apache, is a free and open-source cross-platform web server software. Apache is an extremely popular web service that operates a large portion of the websites on the internet. This article will walk you through the simple process of installing Apache, and opening your server’s firewall up to allow web traffic through.

###Prerequisites:
• Linux based server running CentOS 8

###Step-by-Step:

###Step 1: First, we’ll install our Apache web service which will serve as a base for our application:

# dnf -y install @httpd

###Step 2: Once this is done, we will set it to start on boot and adjust our software firewall:

# systemctl enable --now httpd
# firewall-cmd --add-service={http,https} --permanent
# firewall-cmd --reload

You should now be able to navigate to the IP address of your server in a browser, and see the Apache test page to confirm you’ve configured the server correctly. This page also will display useful information for further configuring Apache to serve your own custom website or application.
