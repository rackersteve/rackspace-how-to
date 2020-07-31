---
permalink: froxlor-initial-setup-and-overview/
audit_date: '2020-07-22'
title: 'Froxlor initial setup and overview'
type: article
created_date: '2020-07-22'
created_by: Rackspace Support
last_modified_date: '2020-07-30'
last_modified_by: Rose Morales
product: Cloud Servers
product_url: cloud-servers
---

This guide will go through the initial setup of Froxlor post installation.

### Prerequisites

- You need a server running a Linux&reg; distribution.
- A user with SSH administrator privileges.

### Settings

1. Select the message **Click here to go to configurations** at the top of the panel.

2. Click on **Settings** under **System** in the left panel.

3. It’s recommended to click on each sub settings menu and look at every option before configuring services.

### Services

1. Once the system settings are ready, click on **Configuration** under **System**. 

2. Copy the PHP script at the bottom and paste it into your server’s terminal. 

    **Note**: Make sure to prepend sudo if you are not logged in as root.

    After you run the script, a series of questions will appear about the server you are running and the services you want to use.

3. Enter the operating system you are using.

4. Select the web, DNS, SMTP, mail, and FTP servers you want to run. Unless you have a preference, select the default values.

5. Next, answer each prompt as required, then enter an empty value once you’ve selected all you need.

6. A new script gets generated to install and configure all the services. Enter “y” to run the script and hit **Enter**.

7. Provide **Administrator** permissions when prompted for the script to complete. Once the installation finishes the message **“All services have been configured”** will display.

### Create a Customer

1. Now we can create our first customer user. Click on **Customers** under **Resources**.

2. Click **Create Customer**.

3. Input the account details.

4. Input contact information.

5. Input quota and access details and click the **Save** button.
