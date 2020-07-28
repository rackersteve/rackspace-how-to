---
permalink: install-gitlab-on-centos-7/
audit_date:
title: 'Install GitLab on CentOS 7'
type: article
created_date: '2020-07-22'
created_by: Rackspace Support
last_modified_date:
last_modified_by:
product: Cloud Product
product_url: cloud-product
---

GitLab Community Edition, or GitLab CE is an open source web based Git repository featuring a wiki and issue tracking. In this guide, we’ll be installing GitLab CE and configuring SSL on a CentOS 7 Cloud Server.

###Prerequisites:
A server with at least 8GB of ram
A domain name pointed at your server.

###Installing Dependencies
Before we can install GitLab, there are a few dependencies needed. Install the packages with yum.

sudo yum install -y curl policycoreutils-python openssh-server postfix
Most if not all of these packages will be installed by default in CentOS 7. During the postfix installation, select Internet Site. On the next page, enter your domain name.

Start and enable Postfix:

sudo systemctl enable postfix && sudo systemctl start postfix

###Installing GitLab CE
Change directory to /tmp:

cd /tmp
Grab the repository script from gitlab.com:

wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh

###Install the repository:

sudo bash script.rpm.sh

###Install GitLab CE:

sudo yum install gitlab-ce

###Configuring GitLab
After the last command, you should have gotten a warning about setting your domain name. While fixing that, we’ll also go ahead and enable SSL with letsencrypt. Open the gitlab configuration file with nano:

sudo nano /etc/gitlab/gitlab.rb
Here you’re looking for the external_url field. Update it to match your domain name and change http to https. It should look something like this once done.

external_url 'https://example.com'
Next, look for the letsencrypt[‘contact_emails’] field. The email addresses here will be alerted if there is ever a problem with your SSL certificate. Once done, it should look something like this:

letsencrypt['contact_emails'] = ['bob@example.com']
Save the file and exit. Now we’ll reconfigure gitlab to have it re-read the new configuration file. This part may take a few minutes.

sudo gitlab-ctl reconfigure
Once the reconfiguration is finished, navigate to your domain name in your web browser to start using GitLab CE!
