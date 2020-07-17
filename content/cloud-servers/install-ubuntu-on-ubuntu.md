---
permalink: install-ubuntu-on-ubuntu/
audit_date:
title: Install nginx on Ubuntu
type: article
created_date: '2020-07-17'
created_by: John Garcia
last_modified_date:
last_modified_by:
product: Cloud Servers
product_url: cloud-servers
---

# Installing Nginx on Ubuntu

Nginx is a web-server service which has gained almost as much market share as Apache in recent years due to its excellent performance and flexible feature set.  This guide will go through installation instructions and discuss next steps in setting up Nginx to serve your site or application.

### Prerequisites:

• Linux server running Ubuntu

## Installing Nginx on Ubuntu

Nginx is available in the default repositories for most popular Linux distributions including Ubuntu.  As such installing it is as simple as running the following apt package-manager commands:

```
sudo apt update
sudo apt install nginx
```

Running update before installing new packages is a best practice, as it allows apt to grab the latest package listings.  This allows the most up-to-date version of the package available on the repository to be the one chosen for installation.

After apt finishes installing the packages, Nginx has been installed.  However, we are not done quite yet.  You should also enable and start the service.  This both sets up Nginx to startup when the server does, as well as starting it up now for further configuration and testing.

```
sudo systemctl enable nginx
sudo systemctl start nginx
```

## Open the firewall for Nginx

By default Nginx will be configured to listen on the default ports for HTTP and HTTPS traffic, 80 and 443 respectively.  However, this does not mean that it will receive traffic, as the firewall on the system will need to also allow traffic on these ports.  Luckily, Nginx makes this easy for us as it registers itself as a service within UFW.  Thus we can simply enable the service on UFW.  Run the following to see what services are available on UFW:

```
sudo ufw app list
```

You should see three options for Nginx, Full, HTTP, and HTTPS.  These services represent both HTTP and HTTPS traffic, just HTTP traffic, and just HTTPS traffic.  Enable the one that is appropriate for your site.  Please note if you wish to have a redirect from HTTP to HTTPS you will want to select Full in this list.  Then simply enable your selection with the following:

```
sudo ufw allow 'Nginx <selection>'
```

**Note:**  Please replace the **<selection>** with the option best suited for your needs.  We recommend only opening the port or ports needed by your application, as minimizing the number of available ports is a security best practice.

## Test Nginx

Once the package is installed and the firewall port or ports are open Nginx should be displaying its default webpage.  You can see this by typing in your IP address in your web browser.  You should see a splash page with Nginx's logo and a "Welcome to Nginx" message.  If you do not see this, double check the IP, that Nginx is running, and the firewall settings.  


## Next Steps

Nginx is now installed and ready to start serving your application or website.  You can utilize the default configuration to serve a site by placing its content at /var/www/html in your filesystem.  However, if you wish to serve more than one site it is recommended that you set up Nginx server blocks to accommodate.
