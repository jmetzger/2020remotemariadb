# MariaDB Administration (Remote) 

## Linux Mariadb Repos installieren 

```
curl -LsS https://downloads.mariadb.com/MariaDB/mariadb_repo_setup | sudo bash
```

## SQL-Mode 

https://mariadb.com/kb/en/sql-mode/#:~:text=SQL_MODE%20is%20used%20for%20getting,commas%20('%20%2C%20')%20without%20spaces.

## Use percona tools on windows 

http://www.jonathanlevin.co.uk/2012/01/query-digest-on-windows.html


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
  
https://mariadb.com/de/resources/blog/flexible-mariadb-server-query-cache/
  
## Windows: Login without Pass

  * If you use mysql with a -u switch, the user, that is logged in to Windows will be used 
  * You can simply test this with "mysql" and without any params.
  * You will then get an error and the user being used will be shown.

You need to install plugin gssapi (which comes with the mariadb installation) 

2 things need be the case that it works

  * Server needs to be in the Domain
  * MariaDB needs be configured to be started with NetworkService 
  
 See more details: 
 https://mariadb.com/kb/en/authentication-plugin-gssapi/
 
## Lock Tables - Who locks tables ?
 
Show open tables helps here - but does not show the user
https://mariadb.com/kb/en/show-open-tables/

The best solution is done with performance_schema 
    
  * Enable performance schema in my.cnf/my.ini peformance_schema=on 
  
  ```
  # Now you can see the user aka connection 
  select th.*,t.* from table_handles th join threads t on th.owner_thread_id = t.thread_id;
  ```
  
