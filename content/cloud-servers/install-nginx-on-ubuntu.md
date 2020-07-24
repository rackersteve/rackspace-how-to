---
permalink: install-nginx-on-ubuntu/
audit_date:
title: Install nginx on Ubuntu
type: article
created_date: '2020-07-17'
created_by: John Garcia
last_modified_date: Rose Morales
last_modified_by: '2020-07-23'
product: Cloud Servers
product_url: cloud-servers
---


Nginx is a web-server service which has gained almost as much market share as Apache in recent years due to its excellent performance and flexible feature set.  This guide will go through the installation instructions and discuss next steps in setting up Nginx to serve your site or application.

#### Prerequisites:

• Linux server running Ubuntu.

### Installing Nginx on Ubuntu

Nginx is available in the default repositories for most popular Linux distributions including Ubuntu.  

- To install run the following apt package-manager commands:

    ```
    sudo apt update
    sudo apt install nginx
    ```

    Running an update before installing new packages allows the most up-to-date version of the package available on the repository to be the one chosen for installation.

- To enable and start the service and add it to the startup, run the following command:

    ```
    sudo systemctl enable nginx
    sudo systemctl start nginx
    ```

### Enable firewall access for Nginx

By default Nginx sends traffic on the default ports for HTTP and HTTPS, 80 and 443 respectively.  However, traffic to be received on these ports needs to be enabled. Nginx makes this easy for us as it registers itself as a service within UFW.

- Run the following command to view available services on UFW:

    ```
    sudo ufw app list
    ```

    **Note**  If you wish to have a redirect from HTTP to HTTPS you will want to select Full.

    | Full | HTTP and HTTPS |
    | HTTP | HTTP only      |
    | HTTPS | HTTPS only    |

- Run the following command to configure the appropriate setting for your site replacing **<selection>** with your choice:

    ```
    sudo ufw allow 'Nginx <selection>'
    ```

    **Note:**  We recommend opening the port or ports needed by your application, as minimizing the number of available ports is a security best practice.

### Test Nginx

- Type the website IP address in the web browser and you should see a splash page with Nginx's logo and a "Welcome to Nginx" message.  If you do not see this:

  - Double check the IP.
  - Check if Nginx is running using:

    `sudo service status nginx`
  - Double check firewall access for Nginx.  


### Next Steps

Now that Nginix is installed and ready to start serving your application or website.  You can utilize the default configuration to serve a site by placing its content at /var/www/html in your filesystem.  However, if you wish to serve more than one site it is recommended that you set up Nginx server blocks to accommodate.
