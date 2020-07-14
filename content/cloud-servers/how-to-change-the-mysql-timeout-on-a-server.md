---
permalink: how-to-change-the-mysql-timeout-on-a-server/
audit_date: '2020-07-13'
title: Change the MySQL Timeout on a Server
type: article
created_date: '2013-07-24'
created_by: Rose Contreras
last_modified_date: '2020-07-13'
last_modified_by: Rose Morales
product: Cloud Servers
product_url: cloud-servers
---

When an application fails to close a unused connection, a low `wait_timeout' value helps avoid
reaching the permitted number of connections.

1. Log in to your server using SSH.

2. Use the sudo command to edit `my.cnf`, MySQL's configuration file.

        sudo vi /etc/my.cnf

3. Locate the timeout configuration and make the adjustments that fit your server.

        wait_timeout = 28800
        interactive_timeout = 28800

    - The `interactive_timeout` value does not affect any web application connections. A low
        `wait_timeout` is normal and is considered best practice.

    - Stateless PHP environments do well with a 60 second timeout or less. Applications that use a
        connection pool (Java, .NET, etc.) will need to adjust `wait_timeout` to match their
        connection pool settings. The default 8 hours = 28800 seconds works well with properly
        configured connection pools.

    - Configuring the `wait_timeout` to be slightly longer than the application connection pool's
        expected connection lifetime as a safety check. Consider changing the value online as it
        does not require a MySQL restart, and it can be adjusted while the running server without
        incurring in downtime. Change the value as `set global wait_timeout=60` and any new sessions
        created would inherit it. Be sure to preserve the setting in `my.cnf`. Any existing
        connections will need to hit the old value of `wait_timeout` if the application abandoned
        the connection. If you do have reporting jobs that will do longer local processing while in
        a transaction, you might consider having such jobs issue `set session wait_timeout=3600`
        upon connecting.

4. Save the changes and exit the editor.

5. Restart MySQL to apply the changes as follows:

        sudo /etc/init.d/mysql restart
