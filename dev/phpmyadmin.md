# phpMyAdmin

install via homebrew

```zsh
brew install phpmyadmin
```

To enable phpMyAdmin in Apache.

Open

```zsh
code /usr/local/etc/httpd/httpd.conf
```

add following

```zsh
Alias /phpmyadmin /usr/local/share/phpmyadmin
<Directory /usr/local/share/phpmyadmin/>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    <IfModule mod_authz_core.c>
        Require all granted
    </IfModule>
    <IfModule !mod_authz_core.c>
        Order allow,deny
        Allow from all
    </IfModule>
</Directory>
```

Restart Apache

```zsh
brew services restart httpd
```

Then open `http://localhost/phpmyadmin`.

The configuration file is `/usr/local/etc/phpmyadmin.config.inc.php`
