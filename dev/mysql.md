# MySQL

Install MySQL@8.4

```zsh
brew install mysql@8.4
```

To secure it run

```zsh
mysql_secure_installation
```

Link mysql to `mysql@8.4`

```zsh
brew link mysql@8.4 --force
brew services restart mysql@8.4
```

Check version

```zsh
mysql -V
```

To connect run

```zsh
mysql -u root -p
```
