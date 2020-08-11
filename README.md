# 2020remote

## Linux Mariadb Repos installieren 

```
curl -LsS https://downloads.mariadb.com/MariaDB/mariadb_repo_setup | sudo bash
```

## SQL-Mode 

https://mariadb.com/kb/en/sql-mode/#:~:text=SQL_MODE%20is%20used%20for%20getting,commas%20('%20%2C%20')%20without%20spaces.

## Partition ##

```
# Only Hints that it works 
https://jira.mariadb.org/browse/MDEV-21189

```

## MySQL Performance Blog ##

https://www.percona.com/blog/

## Mysql copy-back 
```
chown -R mysql:mysql /var/lib/mysql
chmod -R 755 /var/lib/mysql
restorecon -vr /var/lib/mysql
```
