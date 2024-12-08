# PHP

You can see this by running a `<? phpinfo(); ?>` function in a webhosted file or running `php -v` on the command line.

## Install PHP via homebrew

Add the PHP formulae

```zsh
brew tap shivammathur/php
```

Choose the PHP version

```zsh
brew install shivammathur/php/php@8.3
```

or for latest

```zsh
brew install shivammathur/php/php
```

Link the PHP Version

```zsh
brew link --overwrite --force php@8.3
```

Restart the Terminal and Run

```zsh
php -v
```

You should now see the new version. To change to another version just repeat the process from the brew install then unlink and link in the new PHP version by issuing a command like below but with your correct version:

```zsh
brew unlink php && brew link --overwrite --force php@8.2
```

## Getting PHP Working

Open

```zsh
code /usr/local/etc/httpd/httpd.conf
```

Add in required module – example uses PHP 8.3 and PHP 7

```zsh
LoadModule php_module /usr/local/opt/php@8.3/lib/httpd/modules/libphp.so
LoadModule php7_module /usr/local/opt/php@7.4/lib/httpd/modules/libphp7.so
```

Find

```zsh
<IfModule dir_module>
    DirectoryIndex index.html
</IfModule>
```

Change

```zsh
<IfModule dir_module>
    DirectoryIndex index.php index.html
</IfModule>
```

Also at the end of the file add

```zsh
<FilesMatch .php>
    SetHandler application/x-httpd-php
</FilesMatch>
```

Restart Apache

```zsh
brew services restart httpd
```

You can check PHP is running by adding `<?php phpinfo(); ?>` to `index.php` file and view file via `localhost/index.html` in your browser
