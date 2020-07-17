---
permalink: install-nginx-on-windows/
audit_date:
title: Install nginx on Windows
type: article
created_date: '2020-07-17'
created_by: John Garcia
last_modified_date:
last_modified_by:
product: Cloud Servers
product_url: cloud-servers
---

# Installing Nginx on Windows Server

Nginx is a web-server service which has gained almost as much market share as Apache in recent years due to its excellent performance and flexible feature set.  This guide will go through installation instructions and discuss next steps in setting up Nginx to serve your site or application.

### Prerequisites:

• A server running a version of Windows Server

## Installing Nginx on Windows Server

Nginx comes pre-compiled direct from their website, which makes installation as simple as downloading and extracting the file.  You should grab the latest mainline release for Windows from the link below:

http://nginx.org/en/download.html

Once downloaded, simply extract the file to the location you wish to install Nginx at.  We recommend creating a directory for Nginx to live in such as:
```
C:nginx
```

## Test Nginx

Open a CMD prompt and start Nginx with the following:
```
C:nginxnginx.exe
```

Be sure to replace the path if you did not install Nginx in the example directory.  Now you should be able to navigate to http://localhost/ within the server's web browser and see the Nginx default web page.  If you see "Welcome to Nginx" everything is working as intended.

## Items to Note for Nginx on Windows

The Nginx project considers the Windows release for Nginx to be in beta.  It is functionally similar to the Unix releases but some features are missing.  See the link below for more specific details on this.

http://nginx.org/en/docs/windows.html

It is also worth noting that Nginx does not run as a service in Windows, so it will not restart automatically based on your settings within the Local Services options.

## Next Steps

Nginx is now installed and ready to start serving your application or website.  If you wish to serve more than one site it is recommended that you set up Nginx server blocks to accommodate.
