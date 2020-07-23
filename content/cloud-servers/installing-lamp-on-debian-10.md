---
permalink: installing-lamp-on-debian-10/
audit_date:
title: 'Installing a LAMP Stack on Debian 10'
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
• Linux based server running Debian 10

###Step-by-Step:
This part of the guide will go through installing the LAMP stack

Before installing LAMP, we’ll want to make sure your our package management repositories are fully up to date. Run this command to get the latest package listings and update installed packages to their latest versions:

# sudo apt update
After updating, we’ll install Apache, set it to start on boot, and start the service. After which we’ll add a firewall rule to allow port 80 through and make that change persistent:

# sudo apt install apache2
# sudo systemctl start apache2.service
# sudo systemctl enable apache2.service
# sudo iptables -I INPUT -p tcp --dport 80 -j ACCEPT
# sudo iptables-save
Next, we’ll begin installing MariaDB, which is the database that our application will use. These commands will install MariaDB, start the service, and set it to start automatically on boot:

# sudo apt-get install mariadb-server mariadb-client
# sudo systemctl start mariadb.service
# sudo systemctl enable mariadb.service
Now, we can finalize the MariaDB installation by running through MariaDB’s install wizard:

# sudo mysql_secure_installation
When going through the installer, which is optional, you can just answer yes to all the prompts for this guide.

Next, install PHP and some common modules required by various applications. You can always install additional modules if your application requires them:

# sudo apt install php7.3 libapache2-mod-php7.3 php7.3-common php7.3-gmp php7.3-curl php7.3-soap php7.3-bcmath php7.3-intl php7.3-mbstring php7.3-xmlrpc php7.3-mysql php7.3-gd php7.3-xml php7.3-cli php7.3-zip
Finally, we’ll restart Apache once more.

# sudo systemctl restart apache2
You should now be able to navigate to the IP address of your server in a browser, and see the Apache test page to confirm you’ve configured the server correctly. Now our LAMP stack is all set up and ready to act as a base for our application once we install it. It’s important to note that with PHP in particular, there are often additional modules which will be required by whichever application you choose to use. So those will need to be installed also depending on the requirements.
