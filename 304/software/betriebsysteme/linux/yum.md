# yum

#### Show packages

 Lists the repository ID, name, and number of packages it provides for each _enabled_ repository.

```bash
yum repolist
```

#### Remove packages

```text
@todo
```

#### Show available packages

```text
yum list all
```

#### Show installed packages

```text
yum list installed
```

#### Install composer

* [https://www.vultr.com/docs/install-composer-on-centos-7](https://www.vultr.com/docs/install-composer-on-centos-7) 
* [https://linuxize.com/post/how-to-install-and-use-composer-on-centos-7/](https://linuxize.com/post/how-to-install-and-use-composer-on-centos-7/)

```bash
cd /tmp
sudo curl -sS https://getcomposer.org/installer | php
mv composer.phar /usr/local/bin/composer
```

