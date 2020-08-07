---
permalink: install-wordpress-using-a-managed-database-on-debian-10-ubuntu-18-20/
audit_date: '2020-07-24'
title: 'Install WordPress using a managed database on Debian 10, Ubuntu 18.04, and 20.04'
type: article
created_date: '2020-07-24'
created_by: Rackspace Support
last_modified_date: '2020-08-06'
last_modified_by: Rose Morales
product: Cloud Server
product_url: cloud-server
---

WordPress&reg; is a simple content management system based on PHP&reg; and MySQL&reg; and has features that simplify the setup and customization of a website or blog, which is part of what makes it so popular. It is estimated that about one-third of the sites on the internet run on WordPress. In addition to its ease of use, several plugins provide additional features.

This guide describes how to install WordPress, using a remote database separate from our server, to scale in the future.

### Prerequisites

- A Linux&reg; server running the Debian distribution version 10, Ubuntu version 18.04, or 20.04
- A user with SSH administrator privileges

### Create a database

For this article, we’ll create a database called `wordpress` and the username `wpadmin`.

### Creating the sudo user

Sudo users are beneficial because they allow normal users to operate within the server with root user permissions.

1. Log into your server and run the following command to create a new user. Replace `username` with the username you want.

    adduser username

2. Add the new user to the group with administrative privileges.

    usermod -aG sudo username

3. Use the `su` command to switch to our new user and test the sudo access.

    su - userbob

4. You can try running a command now. When using a sudo user, you must place `sudo` before all your commands, as shown in the following example:

    sudo ls -lah

**Note**: If this is the first time you’ve used sudo in a session, you need to enter a password. After you enter the password, the command runs.

### Setting up a LAMP stack

LAMP is an acronym for Linux&reg;, Apache&reg;, MySQL&reg;, PHP&reg;. These are all requirements for a WordPress server.

1. Download all the software required for LAMP and PHP features. Enter **Y** to proceed with each prompt.

    sudo apt install apache2 vim php-curl php-gd php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip

2. Use the following commands to start apache and set it to start on boot.

    sudo systemctl start apache2
    sudo systemctl enable apache2

### Install Wordpress

1. To install WordPress, download the package that contains all the necessary files. Move to the temporary directory to download the tar file. Use the `wget` command to download the package from the official URL provided by WordPress.

    sudo cd /tmp
    sudo wget http://wordpress.org/latest.tar.gz

2. Extract and place it in the Apache web directory to create a WordPress folder at **/var/www/html/wordpress**.

    sudo tar -xvzf latest.tar.gz -C /var/www/html

3. Run the following command to set Apache ownership of that folder.

    chown -R apache /var/www/html/wordpress

4. We recommend that you configure a vhost to serve WordPress to add more sites in the future. To set up the vhost, open the **/etc/httpd/conf/httpd.conf** file with a text editor and add the following code to the end of your file. Remember to change the fields to match your site’s hostname and name log files. The following example uses **wordpress.domain.com** as an example:

    ServerAdmin username@wordpress.domain.com
    DocumentRoot /var/www/html/wordpress
    ServerName wordpress.domain.com
    ServerAlias wordpress.domain.com
    ErrorLog /var/log/httpd/wordpressdomain-error-log
    CustomLog /var/log/httpd/wordpressdomain-acces-log common

5. Open the HTTP port (`80`) for Apache so it can listen for requests over the web:

    sudo ufw allow 80/tcp

### Configure WordPress

1. Navigate to the WordPress directory.

    sudo cd /var/www/html/wordpress

2. Within this directory, rename the Wordpress-provided sample config file to serve as the working config file.

    sudo mv wp-config-sample.php wp-config.php

3. Open **wp-config.php** with a text editor. Search for the following block of code in the file.

    `// ** MySQL settings - You can get this info from your web host ** //
    /** The name of the database for WordPress */
    define( 'DB_NAME', 'database_name_here' );`

    `/** MySQL database username */
    define( 'DB_USER', 'username_here' );`

    `/** MySQL database password */
    define( 'DB_PASSWORD', 'password_here' );`

    `/** MySQL hostname */
    define( 'DB_HOST', 'localhost' );`

4. Replace the values for **database_name_here**, **username_here**, and **password_here** with the matching values that you used for your database. Replace the value for **localhost** with the database's IP address. The result should look similar to the following example:

    `// ** MySQL settings - You can get this info from your web host ** //
    /** The name of the database for WordPress */
    define( 'DB_NAME', 'wordpress' );`

    `/** MySQL database username */
    define( 'DB_USER', 'wpadmin' );`

    `/** MySQL database password */
    define( 'DB_PASSWORD', 'Password!' );`

    `/** MySQL hostname */
    define( 'DB_HOST', '12.34.56.78' );`

5. Add the following lines to the file, replacing **http://example.com** with your site’s URL to prevent a `404` error.

    define('WP_SITEURL', 'http://example.com');
    define('WP_HOME', 'http://example.com');

6. Enable the new site.

    sudo a2ensite wordpress.domain.com.conf

7. Disable the default site.

   sudo a2dissite 000-default.conf

### Test the installation

1. Use the apache2ctl command.

    sudo apache2ctl configtest

2. Restart apache.

    sudo systemctl restart apache2

3. Navigate to http://your.ip.address.here/wp-admin/ to see a WordPress login page.

4. Enter the username and password of the user you created on your server to display the WordPress dashboard where you can configure and customize your site.
