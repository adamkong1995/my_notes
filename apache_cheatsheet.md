# Apache

## Setup virtualhost (Python)
```
<VirtualHost *:99>
        ServerName test.com

        WSGIDaemonProcess test python-home=/var/www/test/env python-path=/var/www/test
        WSGIScriptAlias / /var/www/test/wsgi.py
        DocumentRoot /var/www/test/

        <Directory /var/www/test>
                WSGIProcessGroup test
                WSGIApplicationGroup %{GLOBAL}
                AllowOverride All
                Require all granted
        </Directory>
</VirtualHost>

```

## Setup reverse proxy
```
<VirtualHost *:99>
        ServerName test.com
        ServerAlias www.test.com

        ProxyRequests Off
        ProxyPreserveHost On

        ProxyPass / http://localhost:3000/
        ProxyPassReverse / http://localhost:3000/
</VirtualHost>

```
### Create symbol link for .conf files

`ln -s {origin} {link}`