# Virtual Host

To enable virtual host, Open

```zsh
code /usr/local/etc/httpd/httpd.conf`
```

Find and uncomment

```zsh
#Include /usr/local/etc/httpd/extra/httpd-vhosts.conf
#LoadModule vhost_alias_module lib/httpd/modules/mod_vhost_alias.so
```

Open

```zsh
code /usr/local/etc/httpd/extra/httpd-vhosts.conf
```

Add

```zsh
<VirtualHost *:80>
    DocumentRoot "/Users/shortusername/Sites"
    ServerName localhost
</VirtualHost>

<VirtualHost *:80>
    DocumentRoot "/Users/shortusername/Sites/html"
    ServerName html.test
</VirtualHost>

<VirtualHost *:80>
    ServerName php.test
    DocumentRoot "/Users/shortusername/Sites/php"

    <Directory "/Users/shortusername/Sites/php">
        Require all granted
        AllowOverride All
    </Directory>
</VirtualHost>
```

Open

```zsh
code /etc/hosts
```

Add

```zsh
127.0.0.1 html.test
127.0.0.1 php.test
```
