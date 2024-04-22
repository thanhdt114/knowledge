# Set lower_case_table_names = 1 (linux)

It is mandatory to uninstall mysql and assign values during mysql installation\
**NOTE:**
Please ensure that you have backed up the data in mysql to 1 of your own storage
## Uninstall mysql
1. Stop the MySQL service
```bash
sudo service mysql stop
```
2. Kill all MySQL-related processes
```bash
sudo killall -KILL mysql mysqld_safe mysqld
```
3. Uninstall MySQL installation packages and clean up other associated installation packages
```bash
sudo apt-get --yes purge mysql-server mysql-client mysql-common
sudo apt-get --yes autoremove --purge
sudo apt-get autoclean
```
4. Delete the user and the MySQL group and the user's home directory (if any)
```bash
sudo deluser --remove-home mysql
sudo delgroup mysql
```
5. Delete leftover MySQL-related files and folders
```bash
sudo rm -rf /etc/apparmor.d/abstractions/mysql /etc/apparmor.d/cache/usr.sbin.mysqld /etc/mysql /var/lib/mysql /var/log/mysql* /var/log/upstart/mysql.log* /var/run/mysqld
```

## Reinstall mysql
1. Install MySQL
```bash
sudo apt-get update    
sudo apt-get install mysql-server -y
```
2. Stop the MySQL service
```bash
sudo service mysql stop
```
3. Delete the MySQL data directory
```bash
sudo rm -rf /var/lib/mysql
```
4. Recreate the MySQL data directory (yes, it is not sufficient to just delete its content)
```bash
sudo mkdir /var/lib/mysql    
sudo chown mysql:mysql /var/lib/mysql
sudo chmod 700 /var/lib/mysql
```
5. Add `lower_case_table_names = 1` to the [mysqld] section in /etc/mysql/mysql.conf.d/mysqld.cnf
```bash
sudo gedit /etc/mysql/mysql.conf.d/mysqld.cnf
```
6. Re-initialize MySQL with --lower_case_table_names=1
```bash
sudo mysqld --defaults-file=/etc/mysql/my.cnf --initialize --lower_case_table_names=1 --user=mysql --console
```
7. Start the MySQL service
```bash
sudo service mysql start
```
8. Retrieve the new generated password for MySQL user root
```bash
sudo grep 'temporary password' /var/log/mysql/error.log
```
9. Change the password of MySQL user root either by
```bash
sudo mysql -u root -p
```
and executing
```mysql
ALTER USER 'root'@'localhost' IDENTIFIED BY 'MyNewPa$$w0rd';
```
afterwards, OR by calling the "hardening" script anyway
```bash
sudo mysql_secure_installation
```

## Check the result
1. Access to mysql with root account
```bash
sudo mysql -u root -p
```
2. Executing
```mysql
SHOW VARIABLES LIKE 'lower_case_%';
```
Expected output
```bash
+------------------------+-------+
| Variable_name          | Value |
+------------------------+-------+
| lower_case_file_system | OFF   |
| lower_case_table_names | 1     |
+------------------------+-------+
```
