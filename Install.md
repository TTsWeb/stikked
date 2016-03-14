How To: Install stikked.

# Installing stikked #

Installing stikked at the moment isn't exactly trivial in future releases there will be a wizard but at the moment here's how it goes.

1. Download stikked from http://code.google.com/p/stikked

2. Make sure your server supports PHP5 (PHP4 will not work), apache and MySQL.

> N.B. Your server must have short tags enabled.

3. First create a user and database for Stikked using a tool like phpMyAdmin or the MySQL Administration CLI.

4. Run the following command to setup the database structure;
```
mysql -u username -p databasename < mysql.sql
```
You will be prompted for the password enter it, and it will create the table structure.

5. Configure Stikked
> 5.1 Open /system/application/config/config.php - and edit the base\_url value.

> 5.2 Open /system/application/config/database.php - and fill in the relevant information for your database.

6. You can configure additional options in /system/application/config/stikked.php

7. Configure the cron for auto-expiration (`*`nix only):
> 7.1 Set the key for cron in /system/application/config/stikked.php.

> 7.2 Open a shell and run crontab -e and enter:
```
00, 30 * * * * curl --silent --compressed http://example.com/cron/key > /dev/null 2>&1
```

> 7.3 Save and pray.

8. Remember to edit .htaccess you need to change base\_url to the same one specified in config.php.

9. You should be up and running now, post any bugs to http://code.google.com/p/stikked.