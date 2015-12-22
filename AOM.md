# Bootstrap
## Network
IP

hostname

NIC bonding

## Disk
1. Make partitions

2. 

## Linux
THP (CentOS 6)

Kernel

## Services
### iptables & ip6tables

### NTP

## Databases
### MySQL
```
# yum install -y mysql-server mysql-connector-java
# service mysqld start 
# chkconfig --levels 235 mysqld on
# mysql_secure_installation
# mysqladmin -u root password NEWPASSWORD
```
Edit /etc/my.cnf
```
[mysqld]
character-set-server = utf8
collation-server = utf8_general_ci
```


## Etc
### Port forwarding
```
# nohub socat TCP-LISTEN:11521,fork TCP:9.9.9.9:1521
```
CurrentHost:11521 -> forward -> 9.9.9.9:1521

# Install packages

# Advanced configurations

# Operations

# Backup
## MySQL
### automysqlbackup
http://sourceforge.net/projects/automysqlbackup
```
1. Install
2. Edit /etc/automysqlbackup/myserver.conf
3. Edit crontab
0 4 * * * /usr/local/bin/automysqlbackup /etc/automysqlbackup/myserver.conf > /var/log/mysqlbackup.log
```