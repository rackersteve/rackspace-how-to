---
permalink: installing-lamp-on-fedora-31/
audit_date:
title: 'Installing a LAMP Stack on Fedora 31'
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
• Linux based server running Fedora 31

###Step-by-Step:
This part of the guide will go through installing the LAMP stack.

1) First, we need to set up our repositories so that we can download the latest version of PHP. The following commands will install the Remi repo which will supply this:

# sudo dnf -y install https://rpms.remirepo.net/fedora/remi-release-31.rpm
# sudo dnf config-manager --set-enabled remi
# sudo dnf install dnf-plugins-core
# sudo yum install php73

2) Now we need to Download all the software required for LAMP. The following command strings together a list of packages we’ll install.

# sudo dnf install httpd mariadb mariadb-server php
You’ll be prompted a few times to enter Yes(y) or No(n) as the packages are installed. Press Y to install them.

3) Make sure our version of PHP is v7.3.x with the following command.

# sudo php -v
4) We’ll also need Apache, our web service, running in order to display our site and accept connections. Use the following commands to start Apache, set it to start on boot, and open the firewall for web traffic:

# sudo systemctl start httpd
# sudo systemctl enable httpd
# sudo firewall-cmd --add-service=http --permanent
# sudo firewall-cmd --reload
You should now be able to navigate to the IP address of your server in a browser, and see the Apache test page to confirm you’ve configured the server correctly.

5) We’ll also need to start our database for our application to utilize. The following commands will start our MariaDB database and set it to start on server boot:

# sudo systemctl start mariadb.service
# sudo systemctl enable mariadb.service
Now our LAMP stack is all set up and ready to act as a base for our application once we install it. It’s important to note that with PHP in particular, there are often additional modules which will be required by whichever application you choose to use. So those will need to be installed also depending on the requirements.
