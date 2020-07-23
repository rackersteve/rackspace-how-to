---
permalink: installing-lamp-on-centos-8/
audit_date:
title: 'Installing a LAMP Stack on CentOS 8'
type: article
created_date: '2020-07-22'
created_by: Rackspace Support
last_modified_date:
last_modified_by:
product: Cloud Product
product_url: cloud-product
---

A LAMP Stack is a collection of open-source software that can be used as a platform to create websites and web applications. LAMP itself is an acronym standing for Linux operating system, the Apache HTTP Server, the MySQL database system, and the PHP programming language.

###Prerequisites:
• Linux based server running CentOS 8

###Step-by-Step:
1) First, we’ll install our Apache web service which will serve as a base for our application:

# dnf -y install @httpd
2) Once this is done, we will set it to start on boot and adjust our software firewall:

# systemctl enable --now httpd
# firewall-cmd --add-service={http,https} --permanent
# firewall-cmd --reload
3) Next we’ll install MySQL for our database and set it to start on boot:

# dnf install @mysql:8.0
# systemctl enable --now mysqld
4) Next, we’ll install PHP and some often required PHP modules:

# dnf install -y @php
# dnf install -y php php-{cli,mysqlnd,json,opcache,xml,mbstring,gd,curl}
After this is done, you can check to ensure we’re running PHP and have it display our version of PHP:

# php -v
You should now be able to navigate to the IP address of your server in a browser, and see the Apache test page to confirm you’ve configured the server correctly. Now our LAMP stack is all set up and ready to act as a base for our application once we install it. It’s important to note that with PHP in particular, there are often additional modules which will be required by whichever application you choose to use. So those will need to be installed also depending on the requirements.
