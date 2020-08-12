# MariaDB Administration (Remote) 

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

## Events 
https://mariadb.com/kb/en/events/

## Query Cache 

Does not work well with multiple cores because of mutex.
(Mutual Exclusion Object) 

  * allows multiple program threads to share a resource (such as a folder) 
  * but not simultaneously
  * Mutex is set to unlock when the data is no longer needed
  * or when a routine is finished. 
  * Mutex creates a bottleneck effect. 
  
 
