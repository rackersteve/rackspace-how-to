---
permalink: installing-iis-on-windows-2012/
audit_date: '2020-07-20'
title: 'Installing IIS on Windows 2012'
type: article
created_date: '2020-07-04'
created_by: Travis Gentry
last_modified_date: '2020-07-20'
last_modified_by: Rose Morales
product: Cloud Product
product_url: cloud-product
---

### Install IIS on Windows&#174 2012

This article describes the installation process for Internet Information
Services(IIS) on Windows&#174 server 2012.

#### Limitations

This task requires a user with administrative privileges on the server.

#### Install IIS using Server Manager

1. [Log](https://support.rackspace.com/how-to/connect-to-a-cloud-server/) into
   the server.

2. Press the **Start** button, type **Server Manager** and press **enter**.

3. The **Server Manager Dashboard** window will open.

4. In the upper right-hand corner, click **Manage**.

5. From the drop-down options, click **Add Roles and Features**.

6. The **Add Roles and Features Wizard** will launch.

7. Proceed through the **Add Roles and Features Wizard** until you reach the
   **Server Roles** section.

8. Click the box next to **Web Server (IIS)**, click **Add Features**, and click
   **Next**.

9. Proceed to the **Add Roles and Features Wizard** until you reach the **Role
   Services** section.

    Here, you can keep the default selections, or check role services to install
    for IIS including FTP server, advanced logging options, and more.

10. Select all desired role services and click **Next**.

11. On the **Confirmation** section, you can review your selections as well as
    check the option to restart the server automatically after installation if
    desired.

12. After reviewing the selections, click **Install**.

13. The **Add Roles and Features Wizard** will display a successful installation
    message upon completion.

IIS is now installed on the server. You can go back and install additional role
services at any time. You can configure further using the **IIS Manager**, which
can be found by pressing **Start** and typing **IIS**.

#### Related articles

- [Install IIS and configure a
  website](https://support.rackspace.com/how-to/install-iis-and-configure-a-website/)
- [Configure an IIS FTP
  site](https://support.rackspace.com/how-to/configure-an-iis-ftp-site/)
- [Install an SSL
  certificate](https://support.rackspace.com/how-to/install-an-ssl-certificate/)
- [IIS SNI overview](https://support.rackspace.com/how-to/iis-sni-overview/)
