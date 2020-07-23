---
permalink: installing-lamp-on-ubuntu-1804/
audit_date:
title: 'Installing a LAMP Stack on Ubuntu 18.04'
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
• Linux based server running Ubuntu 18.04

###Step-by-Step:
Before installing LAMP, we’ll want to make sure our package management repositories are fully up to date. Run this command to get the latest package listings and update installed packages to their latest versions:

# sudo apt update
After updating, we’ll install Apache, set it to start on boot, and start the service:

# sudo apt install apache2
# sudo systemctl start apache2.service
# sudo systemctl enable apache2.service
Next, we’ll begin installing MariaDB, which is the database that our LAMP stack will use. These commands will install MariaDB, start the service, and set it to start automatically on boot:

# sudo apt-get install mariadb-server mariadb-client
# sudo systemctl start mariadb.service
# sudo systemctl enable mariadb.service
Now, we can finalize the MariaDB installation by running through MariaDB’s install wizard:

# sudo mysql_secure_installation
When going through the installer, which is optional, you can just answer yes to all the prompts for this guide.

Next, we’ll install PHP, which is the scripting language that the LAMP stack uses. We’ll need to add Ondrej’s repository, which maintains updated PHP packages for us to download and use:

# sudo apt-get install software-properties-common
# sudo add-apt-repository ppa:ondrej/php
# sudo apt update
Next, install the PHP and some modules that many web services require:

# sudo apt install php7.1 libapache2-mod-php7.1 php7.1-common php7.1-gmp php7.1-curl php7.1-soap php7.1-bcmath php7.1-intl php7.1-mbstring php7.1-xmlrpc php7.1-mcrypt php7.1-mysql php7.1-gd php7.1-xml php7.1-cli php7.1-zip
Finally, we’ll restart Apache.

# sudo systemctl restart apache2
You should now be able to navigate to the IP address of your server in a browser, and see the Apache test page to confirm you’ve configured the server correctly. Now our LAMP stack is all set up and ready to act as a base for our application once we install it. It’s important to note that with PHP in particular, there are often additional modules which will be required by whichever application you choose to use. So those will need to be installed also depending on the requirements.
