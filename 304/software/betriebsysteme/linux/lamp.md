# LAMP

## Apache

#### Install Apache

```text
sudo yum install httpd
sudo systemctl enable httpd
sudo systemctl start httpd
```

#### Get Apache status

```text
systemctl status httpd
```

#### Get Apache version

```text
/usr/sbin/httpd -v
```

#### Restart Apache without loosing sessions

```text
apachectl graceful
```

## Install MariaDB

[https://www.tecmint.com/install-mariadb-in-centos-7/](https://www.tecmint.com/install-mariadb-in-centos-7/)

