---
permalink: froxlor-initial-setup-and-overview/
audit_date:
title: 'Froxlor Initial Setup and Overview'
type: article
created_date: '2020-07-22'
created_by: Rackspace Support
last_modified_date:
last_modified_by:
product: Cloud Product
product_url: cloud-product
---

In this guide, we’ll go through the initial setup of Froxlor post installation. If you haven’t yet installed Froxlor, use this article to do so before proceeding.

### Prerequisites

A Cloud Server Running with Froxlor installed
SSH Access as root or an equally privileged user
Settings
For now, ignore the System not configured yet. Click here to go to configurations message at the top of the panel as the setting should be configured before services. To get to settings, click on Settings under System in the left panel.

Here you can configure SSL and a host of other settings. I won’t go over them all in this article as there are so many, but it’s a good idea to click on each sub settings menu and look at every option before configuring services.

###Services

Once the system settings are ready, click on Configuration under System. Here you can either go through the prompts and manually run every command for every service you need, or you can run the PHP script at the bottom. As the script is a bit faster, I’ll be using that. Copy the script and paste it into your server’s terminal. Make sure to prepend sudo if you are not logged in as root.


Once you run the script, you’ll be asked a series of questions about the server you are running and the services you want to use. The first question will be what operating system you are using. For this guide, I’m using Debian 10 (Buster). Make sure to replace that with the operating system you are using.

You’ll then be asked what web, DNS, SMTP, mail, and FTP servers you want to run. Unless you have a preference, the default values are fine.

Next, you’ll be asked about a few more services. Enter each one you want manually and then enter an empty value once you’ve selected all you need.

A new script will then be generated to install and configure all the services. Enter “y” to run the script immediately.

You’ll be prompted for permission to install software a few times before the script is complete. You’ll see a message “All services have been configured” once complete.

###Create a Customer

Now that the services have been configured. We can create our first customer user. Click on Customers under Resources.

Click Create Customer.

Input the account details.

Input contact information.

Input quota and access details.
