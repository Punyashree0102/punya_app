## admin login

- username: admin
- password: admin

### install docker-compose

 ### To execute 
 ```bash
docker-compose up -d --build
```

### To delete
```bash
docker-compose down
```
 
### install mysql on amazonlinux 2

```bash
sudo yum update -y
sudo yum install -y mariadb-server
sudo systemctl start mariadb
sudo systemctl enable mariadb
sudo mysql_secure_installation 
sudo systemctl status mariadb
```
```bash
# Update the MySQL configuration file to allow remote connections
vi /etc/my.cnf

# add these line to my.cnf
bind-address=0.0.0.0
```
```bash
# Restart MariaDB service to apply changes
sudo systemctl restart mariadb

echo "MySQL configuration updated to allow remote connections and MariaDB service restarted."
```
---
### to give Grant access
```bash
mysql -u root -p
```
```bash
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '1234' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```
---
