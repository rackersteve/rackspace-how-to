---
permalink: installing-nginx-on-fedora/
audit_date:
title: Installing Nginx on Fedora
type: article
created_date: '2020-07-21'
created_by: John Garcia
last_modified_date:
last_modified_by:
product: Cloud Servers
product_url: cloud-servers
---

# Installing Nginx on Fedora

Nginx is a web-server service which has gained almost as much market share as Apache in recent years due to its excellent performance and flexible feature set.  This guide will go through installation instructions and discuss next steps in setting up Nginx to serve your site or application.

### Prerequisites:
• Linux server running Fedora

## Installing Nginx on Fedora

Nginx is available in the default repositories for most popular Linux distributions including Fedora.  As such installing it is as simple as running the following dnf package-manager command:

```
sudo dnf install nginx
```
Be sure to hit 'y' for the Y/N prompt to confirm that you wish to install the package.

After dnf finishes installing the packages, Nginx has been installed.  However, we are not done quite yet.  You should also enable and start the service.  This both sets up Nginx to startup when the server does, as well as starting it up now for further configuration and testing.

```
sudo systemctl enable nginx
sudo systemctl start nginx
```

## Open the firewall for Nginx

By default Nginx will be configured to listen on the default ports for HTTP and HTTPS traffic (Ports 80 and 443).  However, this does not mean that it will receive traffic, as the firewall on the system will need to also allow traffic on these ports.  Add the ports necessary for your site by adding the HTTP and/or HTTPS services:

```
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
```

Then reload firewalld to apply the new settings:

```
sudo firewall-cmd --reload
```

## Test Nginx

Once the package is installed and the firewall port or ports are open Nginx should be displaying its default webpage.  You can see this by typing in your IP address in your web browser.  You should see a splash page with Nginx's logo and a "Welcome to Nginx" message.  If you do not see this, double check the IP, that Nginx is running, and the firewall settings. 

## Next Steps

Nginx is now installed and ready to start serving your application or website.  You can utilize the default configuration to serve a site by placing its content at /var/www/html in your filesystem.  However, if you wish to serve more than one site it is recommended that you set up Nginx server blocks to accommodate.
