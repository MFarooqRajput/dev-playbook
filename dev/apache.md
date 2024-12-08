# Apache

## Remove builtin Apache

You can test if Apache is running by issuing this command, which is checking Port 80

```zsh
sudo lsof -i:80
```

Stop Apache running on computer restart by issuing

```zsh
sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist
sudo lsof -i:80
```

## Installing Apache with Homebrew

Install Apache which is known as the package name `httpd`

```zsh
brew install httpd
```

Set Apache to auto-start now and on computer restart

```zsh
brew services start httpd
```

The other 2 commands to stop or Restart Apache are

```zsh
brew services stop httpd
brew services restart httpd
```

By default the Apache Homebrew package is listening on Port 8080 and 8443, test by issuing

```zsh
sudo lsof -i:8080
```

Test the location of Apache/httpd

```zsh
which httpd
```

Homebrew location is: `usr/local/bin/httpd`. If you are getting the default macOS location `/usr/sbin/httpd`. Restart the computer and try the location test again.

## Changing the port number from 8080 to 80

```zsh
code /usr/local/etc/httpd/httpd.conf
```

Find

```zsh
Listen 80
```

Change to

```zsh
Listen 80
```

Restart Apache and web files will now be served over the default port 80.

```zsh
brew services restart httpd
```

## Changing the document root to be the old sites folder

```zsh
code /usr/local/etc/httpd/httpd.conf
```

Find

```zsh
DocumentRoot "/usr/local/var/www"
```

Change to

```zsh
DocumentRoot "/Users/shortusername/Sites"
```

Change the shortusername to the one on your macOS account

Find

```zsh
<Directory "/usr/local/var/www">
```

Change to

```zsh
<Directory "/Users/shortusername/Sites">
```

Find

```zsh
#
# AllowOverride controls what directives may be placed in .htaccess files.
# It can be "All", "None", or any combination of the keywords:
#   AllowOverride FileInfo AuthConfig Limit
#
AllowOverride None
```

Change to

```zsh
#
# AllowOverride controls what directives may be placed in .htaccess files.
# It can be "All", "None", or any combination of the keywords:
#   AllowOverride FileInfo AuthConfig Limit
#
AllowOverride All
```

Find

```zsh
User _www
Group _www
```

Change to

```zsh
User shortusername
Group staff
```

Find

```zsh
#ServerName www.example.com:8080
```

Change to

```zsh
ServerName localhost
```

Find and uncomment

```zsh
LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so
```

Restart Apache

```zsh
brew services restart httpd
```

Now the webroot is `/Users/shortusername/Sites/` just add a `index.html` file there and view file via `localhost/index.html` in your browser

## Apache Log File

To check any Apache errors or access you can find its log files:

```zsh
/usr/local/var/log/httpd/error_log
/usr/local/var/log/httpd/access_log
```
