---
permalink: install-nginx-on-windows/
audit_date:
title: Install nginx on Windows
type: article
created_date: '2020-07-17'
created_by: John Garcia
last_modified_date: '2020-07-24'
last_modified_by: Rose Morales
product: Cloud Servers
product_url: cloud-servers
---

Nginx is a web-server service which has gained almost as much market share as Apache in recent years due to its excellent performance and flexible feature set.  This guide will go through installation instructions and discuss next steps in setting up Nginx to serve your site or application.

#### Prerequisites:

• A server running a version of Windows Server

### Nginx installation on Windows&reg; Server

Nginx comes pre-compiled direct from their website, which makes installation as simple as downloading and extracting the file.  

- Download the latest mainline release from http://nginx.org/en/download.html

- Extract the file to the location you wish to install Nginx.  

    **Note** We recommend creating a new directory for Nginx to live:

    ```
    C:\nginx
    ```

### Test installation

- Open a CMD prompt and start Nginx with the following command:

    ```
    C:\nginxnginx.exe
    ```

    **Note** Replace `C:\` with the directory location where the Nginix was extracted.

Now you should be able to navigate to http://localhost/ within the server's web browser and see the Nginx default web page.  If you see "Welcome to Nginx" everything is working as intended.

### Useful information

The Nginx project considers the Windows release to be in beta.  Functionally is similar to Unix releases but some features are missing.  See the link below for further information.

http://nginx.org/en/docs/windows.html

Nginx does not run as a service in Windows, so it will not restart automatically based on your settings within the Local Services options.

### Next Steps

If you wish to serve more than one site it is recommended that you set up Nginx server blocks to accommodate.
